# Haiku Book Docset

A [Zeal](https://zealdocs.org/) docset containing the complete Haiku API documentation from the [Haiku Book](https://www.haiku-os.org/docs/api/).

## Installation

### NEW - Install via feed

The easiest way to install this docset is to provide Zeal with the [Docset feed](https://raw.githubusercontent.com/Genio-The-Haiku-IDE/org.haiku.HaikuBook.docset/refs/heads/main/HaikuBook.xml).

```
https://raw.githubusercontent.com/Genio-The-Haiku-IDE/org.haiku.HaikuBook.docset/refs/heads/main/HaikuBook.xml
```

Zeal will automatically install the docset and will detect any update available in the future.

### Quick Install

Clone the repository directly to your Zeal docsets directory:

```bash
# Navigate to the Zeal docsets directory
cd /boot/home/config/cache/Zeal/Zeal/docsets

# Clone the repository
git clone https://github.com/Genio-The-Haiku-IDE/org.haiku.HaikuBook.docset/
```

After cloning, restart Zeal and the Haiku Book docset should appear in your available documentation.

## Building from Source

If you want to generate the docset yourself from the Haiku source code, follow these instructions:

### Prerequisites

Install the required tools using HaikuDepot or pkgman:

```bash
pkgman install doxygen doxygen2docset
```

### Step 1: Get Haiku Source Code

Clone the Haiku source code following the [official guide](https://www.haiku-os.org/guides/building/get-source-git/):

```bash
# Create workspace directory
mkdir -p /boot/home/develop
cd /boot/home/develop

# Clone Haiku repository
git clone https://review.haiku-os.org/haiku
```

### Step 2: Configure Doxygen

Navigate to the documentation directory:

```bash
cd haiku/docs/user
```

Edit the `Doxyfile` and ensure the following options are set:

```
GENERATE_DOCSET = YES
GENERATE_HTML = YES
```

For more detailed Doxygen configuration options, refer to the [Doxygen documentation](http://www.doxygen.nl/manual/config.html).

### Step 3: Generate Documentation

Run Doxygen to generate the HTML documentation and docset:

```bash
doxygen
```

The generated files will be placed in `../../generated/doxygen/html/`.

### Step 4: Create Docset

Use doxygen2docset to finalize the docset creation:

```bash
doxygen2docset --doxygen ../../generated/doxygen/html --docset ./HaikuBook.docset
```

### Step 5: Install Generated Docset

Copy the generated docset to your Zeal directory:

```bash
cp -r ./HaikuBook.docset /boot/home/config/cache/Zeal/Zeal/docsets/
```

Restart Zeal to see your newly generated docset.

## About

This docset provides offline access to the complete Haiku API documentation, including:

- Haiku API classes and functions
- Code examples and usage patterns
- Complete reference documentation

The docset is automatically generated from the official Haiku source code documentation to ensure accuracy and completeness.

## Contributing

If you find issues with the docset or want to update it:

1. Fork this repository
2. Make your changes
3. Submit a pull request

For issues related to the documentation content itself, please report them to the [Haiku project](https://dev.haiku-os.org/).

## License

This docset contains documentation from the Haiku project. Please refer to the [Haiku project licensing](https://www.haiku-os.org/about/license/) for details.

## Links

- [Haiku](https://www.haiku-os.org/)
- [Haiku Book (online)](https://www.haiku-os.org/docs/api/)
- [Zeal Documentation Browser](https://zealdocs.org/)
- [Genio - The Haiku IDE](https://github.com/Genio-The-Haiku-IDE)
