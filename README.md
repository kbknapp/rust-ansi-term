rust-ansi-term
==============

This is a library for controlling colours and formatting, such as red
bold text or blue underlined text, on ANSI terminals.


Installation
------------

It uses [Cargo](http://crates.io/), Rust's package manager. You can
depend on this library by adding this Git repository to your Cargo
dependencies.


Usage
-----

You can format strings by calling the `paint` method on a Colour or a
Style object, passing in the string you want to format. Here are some
examples:

```Rust
fn main() {
    println!("Red text: {}", Red.paint("Red!"));
    println!("Red text: {}", Red.normal().paint("Red!"));  // same as above

    println!("Blue bold text: {}", Blue.bold().paint("Blue bold!"));
    println!("Blue bold text: {}", Blue.normal().bold().paint("Blue bold!"));  // same as above

    println!("Yellow underline text: {}", Yellow.underline().paint("Yellow underline!"));
    println!("Blue on yellow text: {}", Blue.on(Yellow).paint("Blue on yellow!"));

    println!("Colour #134: {}", Fixed(134).paint("A sort of light purple."));
    println!("Colour #221 on #124: {}", Fixed(221).on(Fixed(124)).paint("Mustard in the ketchup."));

    println!("No formatting: {}", Plain.paint("No colours here."));
}
```

Available colours are Black, Red, Yellow, Green, Blue, Purple, Cyan, White, and Fixed(n) up to 256. Available formattings are `.bold()`, `.underline()`, and `.on(colour)`.
