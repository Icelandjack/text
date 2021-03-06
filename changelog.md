1.1.1.0

* The Data.Data instance now allows gunfold to work, via a virtual
  pack constructor

* dropEnd, takeEnd: new functions

* Comparing the length of a Text against a number can now
  short-circuit in more cases

1.1.0.1

* streamDecodeUtf8: fixed gh-70, did not return all unconsumed bytes
  in single-byte chunks

1.1.0.0

* encodeUtf8: Performance is improved by up to 4x.

* encodeUtf8Builder, encodeUtf8BuilderEscaped: new functions,
  available only if bytestring >= 0.10.4.0 is installed, that allow
  very fast and flexible encoding of a Text value to a bytestring
  Builder.

  As an example of the performance gain to be had, the
  encodeUtf8BuilderEscaped function helps to double the speed of JSON
  encoding in the latest version of aeson! (Note: if all you need is a
  plain ByteString, encodeUtf8 is still the faster way to go.)

* All of the internal module hierarchy is now publicly exposed.  If a
  module is in the .Internal hierarchy, or is documented as internal,
  use at your own risk - there are no API stability guarantees for
  internal modules!

1.0.0.1

* decodeUtf8: Fixed a regression that caused us to incorrectly
  identify truncated UTF-8 as valid (gh-61)

1.0.0.0

* Added support for Unicode 6.3.0 to case conversion functions

* New function toTitle converts words in a string to title case

* New functions peekCStringLen and withCStringLen simplify
  interoperability with C functionns

* Added support for decoding UTF-8 in stream-friendly fashion

* Fixed a bug in mapAccumL

* Added trusted Haskell support

* Removed support for GHC 6.10 (released in 2008) and older
