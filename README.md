# iban_validate
[![Crates.io](http://meritbadge.herokuapp.com/iban_validate)](https://crates.io/crates/iban_validate)
[![Travis Build Status](https://travis-ci.org/ThomasdenH/iban_validate.svg?branch=master)](https://travis-ci.org/ThomasdenH/iban_validate)
[![Appveyor Build Status](https://ci.appveyor.com/api/projects/status/github/ThomasdenH/iban_validate?svg=true)](https://ci.appveyor.com/project/ThomasdenH/iban-validate)

This is a small crate that is able to validate an IBAN account number.

## Usage
The crate can be found on [crates.io](https://crates.io/crates/iban_validate). To use this crate, just add it as an
dependency:
    
    [dependencies]
    iban_validate = "1.0.1"

## Functionality
This crate provides an easy way to validate an IBAN (International Bank Account Number). To do so, you can use the 
function [`parse()`]. If you want to check whether the address has a valid BBAN (Basic Bank Account Number), you can 
use [`validate_bban()`]. It also contains some helper methods to make handling an IBAN easier.

### Example
The following example does a full validation of the IBAN and BBAN format.

```rust
use iban::Iban;
use iban::BbanResult;

let account = "DE44500105175407324931".parse::<Iban>()?;

assert_eq!(account.validate_bban(), BbanResult::Valid);
assert_eq!(account.get_country_code(), "DE");
assert_eq!(account.get_check_digits(), 44);
assert_eq!(account.get_bban(), "500105175407324931");
```

[`parse()`]: https://doc.rust-lang.org/std/primitive.str.html#method.parse
[`validate_bban()`]: https://docs.rs/iban_validate/1.0.1/iban/struct.Iban.html#method.validate_bban

## Documentation
The full documentation is available at [docs.rs](https://docs.rs/iban_validate/).

## Contributing
If you experience issues with this crate or want to help, please look [here](contributing.md).

## License

Licensed under either of

 * Apache License, Version 2.0
   ([LICENSE-APACHE](LICENSE-APACHE) or http://www.apache.org/licenses/LICENSE-2.0)
 * MIT license
   ([LICENSE-MIT](LICENSE-MIT) or http://opensource.org/licenses/MIT)

at your option.

### Contribution

Unless you explicitly state otherwise, any contribution intentionally submitted
for inclusion in the work by you, as defined in the Apache-2.0 license, shall be
dual licensed as above, without any additional terms or conditions.