Package information of a `.deb` package
====

**Displaying package relations:**

    $ apt-cache showpkg <package>

 * `Dependencies:`          Packages upon which this package depends
 * `Reverse Dependencies:`  Packages that depend upon this package
 * `Provides:`              Additional (virtual) package-names
 * `Reverse Provides:`      Packages that provide the dependencies of this package

Example:

    $ apt-cache showpkg git-core
    $ apt-cache showpkg git
