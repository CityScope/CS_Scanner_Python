# CityScope Scanner and Networker

#### [Python, openCV, NumPy]

This tool is for capturing, key-stoning, scanning and sending uniquely tagged arrays of 2-dimension physical colored bricks. CityScope Scanner will detect colors in arrays of 2d-pixel arrays at sizes of 3x3. Than, these color arrays will be compared to `tags` attribute of a given `json` file [should be located in `data` folder]. At last, the tool will return a list of `type` and `rotation` for each of the scanned arrays. This list can be sent for visualizing using UDP and HTTP.

## Running Regularly / Quick-Run

- Clone this repo, start Terminal at the project's folder
- Run using `$ ./run`
- Tool will start scanning using whatever keystone data was stored in `scanner/data`
- make corrections to the key stone using the sliders. Press `s` to save change to file and `ctrl-c` twice [in the terminal window] to exit program

Note: Running the tool in this way will involve some fail safe mechanisms that will auto-restart the tool when it crashes [such as camera disconnect, slider failure or networking issue]

## Setup and Calibration On First Time Usage / Full Setup

- get python 3.4 and above, clone this repo
- Install packages manually or using `pip` via `pip install -r requirements.txt`
- Run `keystone` with: `$ python3 keystone.py`
- the tool will start, assuming a webcam is connected and working
- Select 4 corners [up right, up left, bottom right, bottom left, at this order] of keystone region
  Note: no need to exactly select the corners, as these are only initial guides for `scanner` tool
- `keystone.py` will create `keystone.txt` and close
- Run `scanner` with `$ python3 scanner.py`. Tool will start scanning using the key stone data created with`keystone.py`
- make corrections to the key stone using the sliders. Press `s` to save changes to file and `ctrl-c` to close program

## Scan results:

```
{"grid":[[-1, -1], [1, 0], [16, 3], [12, 3], [4, 1], [-1, -1], [-1, -1], [-1, -1], [-1, -1], [-1, -1], [-1, -1], [-1, -1], [-1, -1], [2, 2], [-1, -1], [-1, -1], [-1, -1], [-1, -1]]}
```

## Optional

- Use `udp_listener.py` to emulate UDP server listener and test received string

## License

Please see `LICENSE` file for more details.This tool may require libraries which are subject to own licensing.

## Contribution

Please use GitHub Issues and PR interface for contributions.

---

Maintained by [Ariel Noyman](http://arielnoyman.com)

[Repo contributors](https://github.com/CityScope/CS_Scanner_Python/graphs/contributors)
