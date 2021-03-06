# Changelog

## securesystemslib v0.14.0

* *behavior change*
  * Default to pure Python ed25519 signature verification when nacl is unavailable (#200)
  * Fix settings.SUBPROCESS_TIMEOUT access in process module (#202)
* Improve schema-related error message (#199)
* Generally improve optional dependency handling (#200)
* Enhance test configuration, fix typos and remove unused code (#201)
* Fix improper identity check (#203)

## securesystemslib v0.13.1

* Fix MANIFEST.in to include all test data in source release (#196)

## securesystemslib v0.13.0

* Add support for *OpenPGP* EdDSA/ed25519 keys and signatures (#188)
bump
## securesystemslib v0.12.2

* Remove unnecessary `python-dateutil==2.8.0` version pinning to not cause
  downstream dependency conflicts (#192)

## securesystemslib v0.12.1

* Fix stream duplication race conditions in subprocess interface (#186)

## securesystemslib v0.12.0

* *backwards incompatible*
  * Remove data serialization in `create_signature` and `verify_signature` (#162)
  * Replace mostly obsolete `TempFile` utility with single helper function (#181)
  * Remove *TUF*-specific code and comments (#165)
* *new features*
  * Add support for *pkcs1v15* RSA signature scheme and additional hash algorithms (#173, #175)
  * Add basic *OpenPGP* support, transferred from [in-toto](https://github.com/in-toto/in-toto) (#174, #176, #185)
* *miscellaneous*
  * Fix publishing of code coverage  and enhance test configuration (#171)
  * Make colorama a strict dependency (#178)
  * Enhance source distribution metadata (#168)
  * Update downstream Debian metadata (#177)

## securesystemslib v0.11.3

* Provide option to normalize line endings (`\r\n` -> `\n`, `\r` -> `\n`) when
calculating the hash of a file (default: do not normalize).
* Update developer dependencies (dev-requirements.txt):
  * cryptography 2.2.2 to 2.3.1
  * tox 3.0.0 to 3.2.1

## securesystemslib v0.11.2

* No (en|de)cryption of ed25519 key files when given empty password (pr #148).

* Support ed25519 crypto in pure python with default installation (pr #149).

* Update installation instructions to indicate commands needed to install
  optional dependencies for RSA and ECDSA support (pr #150).

* Edit setup.py's license classifier to `OSI LIcense :: MIT` (pr #151).

## securesystemslib v0.11.1

* Convert `\r\n` newline characters to `\n`, so that the same KEYID is
  generated for key data regardless of the newline style used (pr #146).

## securesystemslib v0.11.0

* Add `prompt` parameter to interface.import_rsa_privatekey_from_file() (pr #124).

* Update dependencies

## securesystemslib v0.10.11

* Replace deprecated `cryptography` methods.  signer() and verifier()
  should be replaced with sign() and verify(), respectively.

* Update dependencies.

## securesystemslib v0.10.10

* Add get_password() to API.

* Enable password confirmation in all `generate_and_write_XXX_keypair()`
  functions.

* Minor:
  Fix broken link in comment (recommended # of bits for RSA keys).
  Add `TEXT_SCHEMA`.
  Remove obsolete function (check_crypto_libaries) from `.coveragerc`.

## securesystemslib v0.10.9

* Add `debian` directory (and files) that can be used to package a .deb file.

* Modify functions that generate or import keys so that the key file's path is
  shown if the function prompts for a password.

* Add colorama dependency.  It is used to colorize some of the prompts.

* Update dependencies to their latest version.

* Support KEYID filenames for generated key files.  KEYID filenames are used
  if a filename is not specified.

* Minor edits to comments, indentation, whitespace, etc.

* Modify generate_rsa_key() so that leading and trailing newline characters
  are stripped before generating the KEYID.  This is done so that the
  KEYID generated from imported keys match. Imported PEM keys are
  stripped of any leading and trailing newline characters before the KEYID is
  generated.

## securesystemslib v0.10.8

* Drop support for Python 2.6 and 3.3

* Add support for Python 3.6

* Fix bug in PEM parser. See https://github.com/secure-systems-lab/securesystemslib/issues/54

* Drop PyCrypto and multiple-library support

* Update dependencies

* Verify that the arguments to verify_signature() have matching KEYIDs

* Add a changelog file (this one :)

## securesystemslib v0.10.7
@vladimir-v-diaz vladimir-v-diaz released this on Aug 23 · 79 commits to master since this release

* Implement TAP 9

## securesystemslib v0.10.6
@vladimir-v-diaz vladimir-v-diaz released this on Jul 17 · 127 commits to master since this release

* Fix bug in _get_keyid(), where the hash_algorithm argument to _get_keyid()
was not correctly being used.

## securesystemslib v0.10.5
@vladimir-v-diaz vladimir-v-diaz released this on Jun 14 · 130 commits to master since this release

* Bump cryptography dependency to v1.9.0

* Fix backwards-incompatible change introduced by v1.9.0 of cryptography
(dependency)

## securesystemslib v0.10.4
@vladimir-v-diaz vladimir-v-diaz released this on Jan 23 · 146 commits to master since this release

* Add PUBLIC_KEY_SCHEMA and PUBLIC_KEYVAL_SCHEMA

* Remove ssl_crypto/ssl_commons relics in docstrings

## securesystemslib v0.10.3
@vladimir-v-diaz vladimir-v-diaz released this on Jan 19 · 152 commits to master since this release

* Initial pre-release
