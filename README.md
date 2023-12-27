# Check For Pacman Updates

This check plugin checks for the availability of package updates under **pacman**, e.g. **Arch Linux** and derivatives.  
It allows you to check general package update availability or check specific packages.  

Status values '*warning*' and '*critical*' are determined by

- the values of `--warning` / `--critical`
- the number of (specified) packages for which updates are available

---

- [Usage](#usage)
- [Use with Icinga](#use-with-icinga)
- [Creating a package](#creating-a-package)

## Usage

**Help:**

```
check_pacman v1.0.0

This plugin checks for software updates available for 
'pacman' (Arch Linux and derivatives).

Usage:
check_pacman [-l] [-u] [-w WARNING] [-c CRITICAL] [PACKAGE NAMES]

Options:
  -h, --help
    Print this help.
  -u, --update
    Perform a cache update (pacman -Sy), default: false.
  -l, --list
    Print a list of packages that have updates available, default: false.
  -w, --warning
    Warning threshold for number of packages that have updates available, default: 20.
  -c, --critical
    Critical threshold for number of packages that have updates available, default: 50.

Arguments:
  Positional arguments are treated as package names for which to check
  for updates. If specified, other packages are ignored.
```

---

**Checking for any updates:**

```
./check_pacman
```

```
OK: 7 updates available. |'available_upgrades'=7;20;50;0;
```

---

**Using thresholds:**

```
./check_pacman --warning 3 --critical 10
```

```
WARNING: 7 updates available. |'available_upgrades'=7;3;10;0;
```

---

**Checking for updates for specific packages:**

```
./check_pacman linux pacman docker
```

```
OK: 0 updates available. |'available_upgrades'=0;20;50;0;
```

---

**Checking for updates and printing a list of available updates:**

```
./check_pacman --list
```

```
OK: 5 updates available. |'available_upgrades'=5;20;50;0;
Package            Version
python-aiosignal   1.3.1-5
python-ifaddr      0.2.0-3
python-setuptools  1:69.0.3-1
qt6-base           6.6.1-3
virtiofsd          1.9.0-2
```

## Use with Icinga

If you want to, you can use [this check command definition](./icinga2/check_pacman_command.conf) within [Icinga 2](https://icinga.com/docs/icinga-2/latest/doc/03-monitoring-basics/#integrate-the-plugin-with-a-checkcommand-definition).

If you prefer the graphical aid of [Icinga Director](https://icinga.com/docs/icinga-director/latest/doc/30-Configuration-Baskets/), you can use the provided [Basket](./icinga-director/check_pacman_basket.json).

## Creating a package

If you want to create a package from this, you can run the following:

1. Clone the repository

    ```
    git clone https://github.com/Donien/check_pacman.git check_pacman
    ```

2. Change into the directory

    ```
    cd check_pacman
    ```

3. Build and install the package using the PKGBUILD file

    ```
    makepkg -p PKGBUILD --install
    ```
