# Bar Chart Race Visualization

## Overview

This project visualizes time-series data using an animated bar chart race. The chart illustrates changes in sales data over the last decade for various makers, allowing for an engaging comparison of performance over time.

## Features

- **Animated Bar Chart**: Displays the ranking of makers based on sales data.
- **Customizable Appearance**: Easily adjust the colors, font sizes, and titles.
- **Export Options**: Save the animation as a video file (`.mp4`).

## Requirements

Make sure you have the following libraries installed:

- Python 3.x
- `pandas`
- `matplotlib`
- `bar_chart_race`

You can install the necessary libraries using pip:

```bash
pip install pandas matplotlib bar_chart_race
Usage
Prepare your DataFrame (df), ensuring it is in a wide format where each row represents a single time period and each column represents a maker's sales data.

Clean your data:

python
Copy code
import pandas as pd

# Load your data
df = pd.read_csv('your_data.csv')  # Adjust this line to load your dataset

# Clean the DataFrame
df = df.apply(pd.to_numeric, errors='coerce')  # Convert to numeric, coercing errors
df.fillna(method='ffill', inplace=True)  # Fill missing values
df.fillna(0, inplace=True)  # Handle remaining NaN values
Create the bar chart race animation:

python
Copy code
import bar_chart_race as bcr

anim = bcr.bar_chart_race(
    df=df,
    filename='final.mp4',
    figsize=(26, 15),
    dpi=120,
    orientation='h',
    sort='desc',
    n_bars=10,
    steps_per_period=45,
    period_length=3000,
    title={'label': 'Year wise sales of each Makers from last decade', 'size': 52, 'weight': 'bold', 'pad': 40},
    period_label={'x': .95, 'y': .15, 'ha': 'right', 'va': 'center', 'size': 72, 'weight': 'semibold'},
    bar_label_size=27,
    tick_label_size=27,
    bar_kwargs={'alpha': .99, 'lw': 0},
)
Run your script, and the animation will be saved as final.mp4.

Contributing
Contributions are welcome! If you have suggestions or improvements, please create an issue or submit a pull request.

License
This project is licensed under the MIT License. See the LICENSE file for more information.

Acknowledgements
bar_chart_race - The library used for creating the animated bar chart.
Matplotlib - A plotting library for the Python programming language.
