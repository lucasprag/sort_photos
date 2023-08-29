# sort photos

A script to sort photos by year and month into directories.


## Dependencies

For `exif`, follow [their instructions](https://github.com/tonytonyjan/exif). Quick copy/paste:

```
$ brew install libexif
```

Then install ruby dependencies:

```
$ bundle install
```

## Run

```
$ ./bin/sort_photos copy path/to/source/dir path/to/destination/dir
```

## Behaviour

- the script will create directories following this structure:

```
├── 2022
│   ├── 10\ oct
│   ├── 11\ nov
│   └── 12\ dec
└── 2023
    ├── 1\ jan
    ├── 10\ oct
    ├── 11\ nov
    ├── 12\ dec
    ├── 2\ feb
    ├── 3\ mar
    ├── 4\ apr
    ├── 5\ may
    ├── 6\ jun
    ├── 7\ jul
    ├── 8\ ago
    └── 9\ sept

```

- the sorted photos will be renamed to the date and time that they were taken
- if two or more photos were taking at the exact same time, they will be renamed like `_1.jpg`, `_2.jpg`, etc
- for now the script only copies all the files, it doesn't move them
