^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
Changelog for package better_enums
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

1.0.2 (2021-05-17)
------------------
* Merge pull request `#8 <https://github.com/MisoRobotics/better_enums/issues/8>`_ from MisoRobotics/master
  Merge master back into develop
* Merge pull request `#6 <https://github.com/MisoRobotics/better_enums/issues/6>`_ from MisoRobotics/user/rsinnet/feature/update-cmake
  Update CMake minimum version to 3.5
* Add cloudbuild.yaml
  Add gitlint with Google Cloud Build.
* Update CMake minimum version to 3.5
  Update minimum version to avoid deprecation warning.
* Contributors: Ryan Sinnet

1.0.1 (2021-02-09)
------------------
* Merge pull request `#5 <https://github.com/MisoRobotics/better_enums/issues/5>`_ from MisoRobotics/user/rsinnet/fix/build
  Fix rosdebian build
* Fix rosdebian build
  Add missing install to CMakeLists.txt.
* Merge pull request `#4 <https://github.com/MisoRobotics/better_enums/issues/4>`_ from MisoRobotics/master
  Merge master back into develop
* Merge pull request `#3 <https://github.com/MisoRobotics/better_enums/issues/3>`_ from MisoRobotics/release/1.0.0
  Release/1.0.0
* Contributors: Nikita Kosolobov, Ryan Sinnet

1.0.0 (2018-06-13)
------------------
* Converting into ROS package.
* Specialize map_compare for wchar_t (`#44 <https://github.com/MisoRobotics/better_enums/issues/44>`_)
  Add the template partial specialization:
  struct map_compare<const wchar_t*> {...}
* Fix /W4 level warnings in MSVC++ 2015 (`#41 <https://github.com/MisoRobotics/better_enums/issues/41>`_)
  Remove unused variable names and use underlying class for enum (VS 2012
  and above support strongly typed enums and will warn about incorrect
  usage).
* Add unused attribute to free functions (`#27 <https://github.com/MisoRobotics/better_enums/issues/27>`_)
* Enabled constepxr support for clang-cl.
* Merge pull request `#22 <https://github.com/MisoRobotics/better_enums/issues/22>`_ from cheparukhin/master
  Fix name resolution errors
* Add test for ostream operator
* Resolve clashing global and nested namespace names
  Using better_enums as a nested namespace name along a global better_enums namespace resulted in name clashes.
* Move stream I/O operators to enum namespace
  Stream I/O operators defined in a global namespace caused name resolution errors in some cases.
* Simplified README.
* Contributors: Anton Bachin, Anuradha Dissanayake, Ryan Sinnet, Zsolt Parragi, cheny, cheparukhin

* Converting into ROS package.
* Specialize map_compare for wchar_t (`#44 <https://github.com/MisoRobotics/better_enums/issues/44>`_)
  Add the template partial specialization:
  struct map_compare<const wchar_t*> {...}
* Fix /W4 level warnings in MSVC++ 2015 (`#41 <https://github.com/MisoRobotics/better_enums/issues/41>`_)
  Remove unused variable names and use underlying class for enum (VS 2012
  and above support strongly typed enums and will warn about incorrect
  usage).
* Add unused attribute to free functions (`#27 <https://github.com/MisoRobotics/better_enums/issues/27>`_)
* Enabled constepxr support for clang-cl.
* Merge pull request `#22 <https://github.com/MisoRobotics/better_enums/issues/22>`_ from cheparukhin/master
  Fix name resolution errors
* Add test for ostream operator
* Resolve clashing global and nested namespace names
  Using better_enums as a nested namespace name along a global better_enums namespace resulted in name clashes.
* Move stream I/O operators to enum namespace
  Stream I/O operators defined in a global namespace caused name resolution errors in some cases.
* Simplified README.
* Contributors: Anton Bachin, Anuradha Dissanayake, Ryan Sinnet, Zsolt Parragi, cheny, cheparukhin

0.11.1 (2016-03-14)
-------------------
* Bumped version to 0.11.1.
* Fixed old-style cast warnings.
* Documentation nits.
* Enabled more warnings during testing.
  To avoid problems with warnings in CxxTest, the extra warnings are
  enabled during one test (linking) that does not use CxxTest.
  Resolves `#16 <https://github.com/MisoRobotics/better_enums/issues/16>`_.
* Local testing on more versions of Clang.
* Removed double underscores from macro names.
  Names containing (and not only beginning with) double underscores are
  reserved in C++.
  Resolves `#15 <https://github.com/MisoRobotics/better_enums/issues/15>`_.
* README nit.
* Incorporated errata.
  Fixes `#13 <https://github.com/MisoRobotics/better_enums/issues/13>`_.
  Fixes `#14 <https://github.com/MisoRobotics/better_enums/issues/14>`_.
  [ci skip]
* Disabled constexpr testing on MSVC.
  Until recently, CMake reported VS2015 as not supporting constexpr.
  However, constexpr support was added in the VS2015 release, and CMake
  now reports accordingly.
  The constexpr support in VS2015 is too buggy to build Better Enums.
  This change disables testing on VS2015 with constexpr support, because
  those tests will fail.
  Also adapted to a change in the Cygwin path prefix in AppVeyor and
  fixed an issue in the Travis build with wget being unable to retrieve
  from www.cmake.org's new redirect to cmake.org.
* Fixed README.
* Contributors: Anton Bachin, Mikhail Ovchinnikov, Mitsutaka Takeda

0.11.0 (2015-10-05)
-------------------
* Updated documentation.
* Reordered some member functions.
  Microsoft's incomplete constexpr implementation does not currently
  allow constexpr use of constexpr functions that are defined out of line
  below their point of use. The reordering in this commit is a
  workaround.
  While this still doesn't give MSVC constexpr support due to additional
  bugs in Microsoft's implementation, maintaining the member functions in
  this order makes it easier to begin each attempt to work around the
  remaining compiler bugs.
* Added Clang++ 3.7 to test matrix.
* Made default constructor customizable by a macro.
  By default, Better Enums will generate with an inaccessible (private or
  deleted) default constructor. However, if the user defines
  BETTER_ENUMS_DEFAULT_CONSTRUCTOR(Enum), the expansion of that macro
  will be used instead. The macro approach was chosen because the
  expansion can include access modifiers and fragments such as
  "= default".
  Resolves `#10 <https://github.com/MisoRobotics/better_enums/issues/10>`_.
* Fixed example/Makefile.
* Eliminated non-integral underlying types.
  This was an experimental feature. Removing it to simplify maintenance.
* Fixed #ifdef that caused some tests not to run.
  Disabled some tests that were failing due to unsupported type traits in
  Travis standard library installation.
* Renamed top-level macro ENUM to BETTER_ENUM.
  To reduce name clashes.
  Fixes `#11 <https://github.com/MisoRobotics/better_enums/issues/11>`_.
* Replaced testing on G++ 5.1 with G++ 5.2.
  GCC 5.2 is a "bugfix" release over GCC 5.1 - not sure why the GCC team
  updated the minor version number. Package managers seem to have dropped
  GCC 5.1 and replaced it with 5.2, and I'm guessing usage of 5.1 is
  discouraged. The testing code has been updated accordingly.
  Travis is still distributing GCC 5.1 as of the time of this writing.
* Updated AppVeyor configuration.
  Since VS2015 RTM, AppVeyor provides an image that has both VS2015 and
  Cygwin pre-installed. Before this change, I had combined the build
  matrix into one row, because of the need to install Cygwin in each
  build worker, which is a 10-15-minute process. Since this is no longer
  necessary, the matrix is restored. AppVeyor builds are now very fast.
* Bidirectional maps between enums and any types.
  Also added a C++14 configuration to testing, but using it only for
  bidrectional map testing at the moment.
* Restored clang 3.6 and 3.5 in the Travis build.
  Now that llvm.org is back up and Travis is able to download the
  compiler binaries.
* Updated documentation.
* Made N4428 implementation more exact.
  See http://www.open-std.org/jtc1/sc22/wg21/docs/papers/2015/n4428.pdf
* Temporarily removed clang 3.5 and 3.6 in Travis.
  I am still testing against these locally. Travis is having difficulty
  installing them in build instances, perhaps due to the current llvm.org
  outage.
* Fixed bug that disallowed some constant names.
  The user-supplied constant names are used to declare an internal enum
  type. They end up sharing a namespace with some internal library
  values. Those internal values had names not prefixed with underscores.
  As a result, it was impossible to declare enum constants with these
  names.
  Prefixed the internal names with underscores.
* Simple implementation of N4428 enum reflection.
* Local testing on VC2010 and VC2012.
  Also improved the documentation Makefile not to re-generate the samples
  unless the source Markdown files are newer. This should make samples
  development easier.
* Contributors: Anton Bachin

0.10.1 (2015-07-09)
-------------------
* Updated documentation and appearance.
* Included VC2008 in AppVeyor and local testing.
  Also reordered compilers so that the very first tested are the ones
  that support the most configurations, then immediately followed by
  those which are the most likely to fail. Typically, this would be the
  oldest ones, or the compiler versions that were the first to support
  some major features.
* Added workarounds for VC2008.
  VC2008 has two quirks. It generates linking errors if a copy
  constructor is not explicitly defined on a Better Enum, and it has a
  buggy interaction between the ternary operator and throw. This change
  detects VC2008 and generates alternative code for that compiler.
  Having an explicitly-defined copy constructor in a literal type appears
  to cause an internal compiler error in g++4.7, and causes a spurious
  compilation failure in g++4.8. For this reason, the copy constructor
  generation is conditioned on the compiler.
  The replacement code for the ternary operator is also generated
  conditionally, because it uses an if-statement. The normal code has to
  compile in a constexpr context, and so has to use the ternary operator
  instead of the if-statement.
  Resolves `#6 <https://github.com/MisoRobotics/better_enums/issues/6>`_.
* Sped up the AppVeyor build.
  Current AppVeyor images with VC2015 don't have Cygwin pre-installed, so
  each row in the build matrix installs it before running the build. This
  takes about 7-8 minutes per row.
  This change combines all the VC testing into one row, so the price of
  installing Cygwin is paid only once. A secondary improvement is that
  individual rows don't have to wait in the AppVeyor queue. Builds now
  take a total of about 15 minutes, instead of approximately an hour,
  including queueing time.
  This change should probably be undone once there is an AppVeyor image
  that comes with both VC2015 and Cygwin. The main AppVeyor image has VC
  up to 2013 and Cygwin, so I suppose VC2015 and Cygwin will be available
  once a final version of VC2015 is released.
  Until then, Better Enums does not have the benefit of separate rows in
  the AppVeyor build matrix.
* Updated CONTRIBUTING.md and related information.
* Added support for testing in Travis.
* Not assuming bash in testing scripts.
* Support for testing in AppVeyor.
  Tests are run for VC2010, VC2012, VC2013, VC2015.
* Switched to CMake for building tests.
  To run tests with the system compiler, execute
  make
  To run tests with the system compiler in all configurations,
  make default-all
  To re-generate the examples from the documentation Markdown, and then
  test all configurations,
  make default-thorough
  Other Makefile targets are for exhaustive testing with multiple
  locally-installed compilers, or for use on CI servers, and are not for
  general use.
  Python and CxxTest are still required. On Windows, it is helpful to
  have a Cygwin environment with a non-Cygwin CMake, and MSBuild.exe
  should be in PATH.
  Better Enums is now tested in fewer configurations. C++11 features are
  no longer tested on clang 3.3, gcc 4.3-4.6, because CMake claims
  (apparently falsely, in some cases) that those compilers don't support
  constexpr and enum class.
* Fixed char16_t and char32_t detection for clang.
  These are now only assumed in C++11 mode. long long is also assumed
  only in C++11 mode for clang, which may make some programs that rely on
  long long as an extension in C++98 fail with Better Enums. I will solve
  that at a later date if it becomes a problem.
* Only apply the Cygwin fix on Windows.
  The so called 'cygwin_fix_command' replaces all instances of '/home'
  with 'C:/cygwin/home'. This will cause the tests to fail on linux as
  this directory does not exist there.
* Made it easier to generate offline documentation.
  Documentation can be generated by going to doc/ and running "make".
  This requires Python. Before this change, the user had to install the
  mistune library, which is used by the generator. The mistune library is
  now included in the Better Enums distribution.
  The generated docs are available at doc/html/index.html. Note that some
  links won't be local (the GitHub repo, the download link, outgoing
  links to MSDN, tutorial source in the GitHub repo, and so on). All the
  pages belonging to the actual docs will be local, however.
  The online version of the docs can be generated by running "make web".
  The only difference between the online and offline versions is that the
  former includes Google Analytics tracking code, and may include social
  communication buttons, comment section, or other useless things in the
  future.
  Also included errata since the last release.
  Resolves `#2 <https://github.com/MisoRobotics/better_enums/issues/2>`_.
* Updated README.
* Contributors: Alexander Buddenbrock, Anton Bachin

0.10.0 (2015-06-20)
-------------------
* Updated documentation.
* Fixed some warnings with strict flags.
* Changed _size to a function.
  An alternative constant _size_constant is provided for use in C++98,
  for example for declaring arrays.
  Also renamed underlying_traits to integral_mapping.
* Simplified underlying type traits.
  Removed the function are_equal. Comparison is now done by converting
  operands to their integral representation, and comparing those. Also
  restored ordering of enum values along the same lines (according to
  integral representation).
* Initialization now always completed before main.
  Before this change, in C++98 and C++11 "fast" mode, initializer
  trimming was done "lazily" the first time _to_string or _names was
  called. To make performance more "predictable", an object with static
  storage is now used to force initializaton during program start-up,
  when static object constructors are called.
  The benefit of this change is very debatable. I had to give the static
  object static linkage to avoid duplicate symbols, so there is a copy
  now in each translation unit. I hope this does not increase code size
  too much in realistic scenarios.
  Lazy initialization checks are still performed and cannot be removed,
  because other objects with static storage may try to use an enum from
  their constructors before the enum's initialization is forced.
* Internal clean-up.
* Eliminated dynamic allocation.
  When compile-time stringized constant name trimming is disabled (off by
  default), trimming happens "lazily" - the first time the user calls a
  function such as _to_string, the function allocates space for trimmed
  constant names and trims them there.
  With this change, space is reserved statically in a writeable char
  array, and trimming happens in that array instead.
* Made enum.h build with exceptions disabled.
  Throwing functions are simply omitted.
* Included enum type names in exception messages.
* Internal improvements to stream operators.
* Overloaded stream operators.
  To avoid paying the huge penalty of including iostream and string for
  users that don't need those headers, and to avoid creating a second,
  optional header file, I resorted to defining the operators as templates
  to prevent type checking until the user tries to actually use them. The
  stream types and strings are wrapped in a metafunction that depends on
  the template parameter. This is basically a hack, but it seems to work.
* Experimental generalization of underlying types.
  With this change, the underlying type can be a non-integral type that
  provides conversions to and from an integral type. See the test at
  test/cxxtest/underlying.h for some examples - though they are more
  verbose than strictly necessary, for testing needs.
  Move constructors in underlying types are not supported. It has been
  difficult so far to get constexpr code not to select the move
  constructor, which is generally not constexpr, for various operations.
* Improved test.py to for multiple test files and Cygwin.
* Made ENUM usable in namespaces.
* Updated contact information and other errata.
* Added CONTRIBUTING file and acknowledgements.
* Eliminated underscored internal macro names.
  Also made a few documentation changes.
* Contributors: Anton Bachin

0.9.0 (2015-06-05)
------------------
* Updated and improved documentation.
* Made the test script use only the system compiler by default and extended some
  support to VC++.
  The unit test is currently not being run on VC++ due to a problem with CxxTest,
  Cygwin, and paths. However, the examples are being compiled and having their
  output checked, and the multiple translation unit test is being run.
  Running "(cd test ; ./test.py)" should now run tests only using the default
  compiler, on a Unix-like system. test.py --all runs tests on the full array of
  compilers that I have installed and symlinked on my development machines.
* Ported to Microsoft Visual Studio.
  Worked around a bug with vararg macro expansion in VC++ and tested with Visual
  Studio 2013. This commit does not include exhaustive tests for that compiler as
  for clang and gcc. They are coming in a follow-on commit.
  https://connect.microsoft.com/VisualStudio/feedback/details/521844/variadic-macro-treating-va-args-as-a-single-parameter-for-other-macros
* Complete documentation and testing overhaul.
  The documentation is now generated from markdown. Samples are generated from the
  tutorial pages. Testing is done by a Python script which runs the tests for a
  large number of compilers.
  This version is not very developer-friendly - the Python scripts need ways of
  limiting what compilers they try to run. If you don't have 15 compilers
  installed, you won't be able to run the tests in this commit. Fix coming soon.
* Simplified enum.h.
  This patch contains several minor changes.
  - Eliminated the use of a deleted constructor in C++11. C++98 private default
  constructor is sufficient.
  - Eliminated old namespace _enum and merged it with namespace better_enums.
  - Prefixed size_t with std:: to comply with standards more strictly.
  - Shortened feature control macros by deleting the word "FORCE".
  Also moved make_macros.py.
* Rewrote unit tests to work for multiple configurations.
* Fixed bug with missing constructor deletion, removed reference to nullptr.
* Renamed some constants and pp_map_gen.py.
* Made enum class (strict) conversion opt-in on a global basis.
  This makes C++98 and C++11 Better Enums fully compatible by default. If the user
  defines BETTER_ENUMS_FORCE_STRICT_CONVERSION before including enum.h, it is
  necessary to prefix enum constants in switch cases with '+', but Better Enums
  are not implicitly convertible to integers.
* Made all-constexpr (slow) enums an opt-in feature.
* Used explicit inline functions to simplify type hierarchy, also simplified iterables names.
* Fixed problem with multiple compilation units under C++98.
* Refactored using more higher-order macros.
* Made comparison operators global to simplify them.
* Prefixed .to\_* methods with underscores to avoid name conflicts.
* Fixed incorrect definition of optional::operator ->.
* Renamed remaining uppercased types in public interface to lowercase.
* Modifications to support aggressive compiler warning levels.
  These modifications ensure enum.h can be used in a wider
  selection of end user projects without triggering warnings.
  GCC 4.9.2 was used with the following warning flags set:
  -Wall -Wextra -Wshadow -Weffc++ -Wno-unused-parameter
  -Wno-unused-local-typedefs -Wno-long-long -Wstrict-aliasing
  -Werror -pedantic -std=c++1y -Wformat=2 -Wmissing-include-dirs
  -Wsync-nand -Wuninitialized -Wconditionally-supported -Wconversion
  -Wuseless-cast -Wzero-as-null-pointer-constant
  This commit includes the modifications required to enable successful
  use of enum.h via both the "test" and "example" directories.
* Port to C++98 with variadic macros.
  enum.h tries to automatically detect whether it is running with C++11 support.
  If not, it emits alternative code that is supposed to work on compilers
  supporting C++98 and variadic macros. This code is largely interface-compatible
  with the C++11 code, with the following semantic differences:
  - No compile-time stringization. This is done upon first use of a function other
  than to_integral.
  - Implicit conversion to integral types. This is due to the lack of enum class
  support.
  - The values _name, _names, _values are replaced with functions _name\_, _names\_,
  _values\_.
* Forbade nearly all implicit conversions to integral types.
  Each Better Enum now has an internal enum class type to which it is convertible,
  instead of being convertible to the regular enum that defines its constants.
  switch statements are compiled at the enum class type. This comes at the price
  of the user having to type +Enum::Constant instead of Enum::Constant in cases,
  in order to trigger an explicit promotion of the pre-C++11 enum to Better Enum,
  so it can then be implicitly converted to the enum class.
  The remaining "hole" is that direct references to constants (Enum::Constant) are
  still implicitly convertible to integral types, because they have naked
  pre-C++11 enum type.
* Added non-throwing versions of enum introduction functions.
  These return values of an optional type better_enums::optional<T>. This type is
  defined in the spirit of boost::optional<T> and std::optional<T>, but is easy to
  manipulate at compile time. Two additional macros BETTER_ENUMS_USE_OPTIONAL and
  BETTER_ENUMS_EXTRA_INCLUDE are honored, whose intent is for the user to be able
  to inject an alternative option type. However, there are currently no viable
  alternatives. boost::optional<T> does not play well with constexpr, and I failed
  to make the code compile with std::optional<T>. I did not try very hard. I
  intend to support std::optional<T> in the future. Perhaps it will be the
  default, when available.
* Removed range properties.
  They can now be easily computed using the random access iterators. There appears
  to be a slight performance improvement.
* Option to opt in to implicit conversion to enum class instead of enum.
  A Better Enum is normally implicitly convertible to its internal enum type,
  which makes it then implicitly convertible to an integer as well. The former
  conversion is necessary for Better Enums to be usable in switch statements.
  This change makes it possible to define BETTER_ENUMS_SAFER_SWITCH, which makes
  Better Enums convert to an enum class, preventing the implicit conversion to
  integers. The drawback is that switch cases have to be written as
  case Enum::_Case::A:
  instead of
  case Enum::A:
* Minimally updated documentation.
* Subscript operator for iterables and tests for constexpr iterators.
* Made to_string conversion constexpr and removed the last of the weak symbols.
  The interface is now uniformly constexpr, including to_string and the _names
  iterable. Without the weak symbol, the remaining code is also entirely standard
  C++.
  The compile-time string trimming code in this commit has a negative impact on
  performance. The performance test is now twice as slow as including <iostream>,
  whereas before it was faster. That test declares an excessive number of enums,
  though, so perhaps in typical usage, and with some future optimizations, the
  impact will not be so significant.
  There may be other ways to solve this, such as providing a version of the macro
  that does not trim strings at compile time, but only checks if they need
  trimming. If some string does need trimming, that macro would fail a
  static_assert and ask the user to use the slow macro.
* Removed most weak symbols. Iterators should now be random access.
  The remaining weak symbol will be removed when string conversions become
  constexpr. Iterator are random access because they are now pointers.
* Eliminated separate map macro file and inlined its contents into enum.h.
* Updated documentation with new front page.
* Added contact information to README.
* Contributors: Anton Bachin, Ben Alex

0.8.0 (2015-05-11)
------------------
* Initial release.
* .gitignore
* Contributors: Anton Bachin
