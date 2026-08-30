# Helper method for installing Virtuoso Server

Installation helper for Mac and Windows machines. By default, method
will download and launch the official `.dmg` or `.exe` installer for
your platform, running the standard drag-n-drop installer or interactive
dialog. Setting `ask = FALSE` will allow the installer to run entirely
unsupervised, which is suitable for use in scripts. Mac users can
alternatively opt to install Virtuoso through HomeBrew by setting
`use_brew=TRUE`. Linux users should simply install the
`virtuoso-opensource` package (e.g. in debian & ubuntu) using the
package manager or by contacting your system administrator.

## Usage

``` r
vos_install(ask = is_interactive(), use_brew = FALSE)
```

## Arguments

- ask:

  Should we ask user for interactive installation?

- use_brew:

  Should we use homebrew to install? (MacOS only)

## See also

[`vos_start()`](https://docs.ropensci.org/virtuoso/reference/vos_start.md),
[`vos_uninstall()`](https://docs.ropensci.org/virtuoso/reference/vos_uninstall.md)

## Examples
