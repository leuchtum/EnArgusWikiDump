# EnArgusWiki

[![CC BY-SA 4.0][cc-by-sa-shield]][cc-by-sa]

This is a small CLI to retrieve data from the EnArgus Wiki.

# Installation

This tool is on PyPI, so you can easily install it with

```python
pip install enarguswiki
```

**Note:** Only tested on MacOS. Should work on other platforms as well.

# Usage

## Search for something

You can search for something in different languages.

```shell
> enarguswiki search sun --language EN
       Search results for 'sun' in EN

┏━━━━━━━━━━┳━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┓
┃ ObjectID ┃ Name (EN)                      ┃
┡━━━━━━━━━━╇━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━┩
│  2120759 │ Radiation intensity of the sun │
│  2121098 │ diurnal cycle of the sun       │
│  2119926 │ Sun sensor                     │
└──────────┴────────────────────────────────┘
````

## Get a page

```shell

>  enarguswiki page --query "Sun sensor" --language EN

┌────────────┬─────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│ Object ID: │ 2119926                                                                                                 │
├────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│  Language: │ en                                                                                                      │
├────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│      Name: │ Sun sensor                                                                                              │
├────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│   Content: │ A sun sensor determines the radiation intensity of the sun and/or the azimuth angle of a solar power    │
│            │ plant. Sun sensors are used in the design and automatic tracking of a solar power plant. The data       │
│            │ determined by the sun sensor is used to either rigidly position the solar collectors or solar modules   │
│            │ in the most advantageous position during installation or to align them optimally towards the sun with   │
│            │ the help of a tracking system.                                                                          │
│            │ Solar sensors can also be used in the monitoring system of a photovoltaic system. In these systems, │
│            │ they are used to record the irradiated solar power and enable a comparison with the yield of the        │
│            │ system.                                                                                                 │
│            │ Synonym(s):                                                                                             │
│            │ radiation sensor, irradiation sensor, solar sensor, photosensor, photosensor, detector, radiation       │
│            │ meter, light meter                                                                                      │
│            │ German translation(s):                                                                                  │
│            │ Sonnenlichtmesser, Photosensor, Lichtsensor                                                             │
└────────────┴─────────────────────────────────────────────────────────────────────────────────────────────────────────┘
```

Or you can search by the dokument ID:

```shell
>enarguswiki page --oid 2119926

┌────────────┬─────────────────────────────────────────────────────────────────────────────────────────────────────────┐
│ Object ID: │ 2119926                                                                                                 │
├────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│  Language: │ en                                                                                                      │
├────────────┼─────────────────────────────────────────────────────────────────────────────────────────────────────────┤
│      Name: │ Sun sensor                                                                                              │
...
```

Pages can be exported to PDF:

```shell
> enarguswiki page --oid 2119926 --format pdf --out out.pdf
```

This will print a basic pdf:
![](static/sun-sensor.png)

Exporting to JSON is possible as well.

## Get a collection

You can completely dump the Wiki by running

```bash
> enarguswiki collection --language EN --update all
Updating pages...  ╸━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━   2% 0:05:30
````

# License

This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg
