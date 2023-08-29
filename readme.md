# Sort photos

A script to sort photos & videos by year and month into directories.

![Example of directories](/dir_example.png)


## Dependencies

For photos, I'm using [exif](https://rubygems.org/gems/exif) which depends on `libexif` on Mac. Follow [their setup instructions](https://github.com/tonytonyjan/exif), but in a nutshell:

```
$ brew install libexif
```

For videos, I'm using [streamio-ffmpeg](https://rubygems.org/gems/streamio-ffmpeg) which depends on `ffmpeg` on Mac. Follow [their setup instructions](https://github.com/streamio/streamio-ffmpeg?tab=readme-ov-file#ffmpeg), but basically:

```
$ brew install ffmpeg
```


Finally, install ruby dependencies:

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
│   ├── 10-Oct
│   ├── 11-Nov
│   └── 12-Dec
└── 2023
    ├── 1-Jan
    ├── 2-Feb
    ├── 3-Mar
    ├── 4-Apr
    ├── 5-May
    ├── 6-Jun
    ├── 7-Jul
    ├── 8-Ago
    ├── 9-Sept
    ├── 10-Oct
    ├── 11-Nov
    └── 12-Dec

```

- the sorted photos will be renamed to the date and time that they were taken
- if two or more photos were taking at the exact same time, they will be renamed like `_1.jpg`, `_2.jpg`, etc
- for now the script only copies all the files, it doesn't move them
