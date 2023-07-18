# stats-gl

stats-gl is a simple, yet powerful JavaScript library designed to help you monitor and visualize your web application's performance in real-time. The library provides panels that display Frames per Second (FPS), Central Processing Unit (CPU) usage, and if supported, Graphics Processing Unit (GPU) usage.

Note: GPU Monitoring will be available on Safari after the v17 release.

## Table of Contents
- [Description](#description)
- [Installation](#installation)
- [Example Usage](#example-usage)
- [Parameters](#parameters)
- [Contributing](#contributing)
- [License](#license)

## Description

The Stats class exposes methods to create performance panels, log performance metrics, and manage the display and layout of these panels. The performance metrics are logged for FPS CPU and GPU. The GPU logging is only available if the user's browser supports the WebGL 2.0 `EXT_disjoint_timer_query_webgl2` extension.

In addition to logging real-time performance data, the class also provides methods to calculate and display average performance metrics over a specified interval.

## Installation

Stats.js is available as an npm package. You can install it using the following command:

```bash
npm install stats-gl
```

## Example Usage

Below is an example of how you can use this class in your code:
```js
import Stats from "stats-gl";

// create a new Stats object
const stats = new Stats({
    logsPerSecond: 20, 
    samplesLog: 100, 
    samplesGraph: 10, 
    precision: 2, 
    minimal: false, 
    mode: 0 
});

// append the stats container to the body of the document
document.body.appendChild( stats.container );

// begin the performance monitor
stats.begin();

// end the performance monitor
stats.end();
```

## Parameters
The constructor for the Stats class accepts an options object with the following properties:

- logsPerSecond: How often to log performance data, in logs per second.
- samplesLog: Number of recent log samples to keep for computing averages.
- samplesGraph: Number of recent graph samples to keep for computing averages.
- precision: Precision of the data, in number of decimal places.
- minimal: A boolean value to control the minimalistic mode of the panel display. If set to true, a simple click on the panel will switch between different metrics.
- mode: Sets the initial panel to display - 0 for FPS, 1 for CPU, and 2 for GPU (if supported).

All the parameters are optional and have default values. The class also provides other methods such as begin(), end(), init(canvas), etc. which can be used based on the requirement.

Note: The init(canvas) method is used to start the GPU monitoring and must be called with a canvas context before begin().

## Contributing
We welcome contributions to Stats.js. Before contributing, please read our contributing guidelines and code of conduct.

Please report any issues or bugs you encounter.

## License
This project is licensed under the MIT License.