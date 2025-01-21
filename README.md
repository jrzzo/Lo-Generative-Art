# Lo-Generative-Art

## Introduction

The **Lo Generative Art** project uses randomization, color palettes, shapes, and a rarity system to create unique art pieces. The project leverages generative art principles, influenced by geometry, minimalism, and chaos theory, combined with Web3 concepts.

This project uses **Processing** (Java-based framework) to generate each art piece and calculates a **rarity score** based on the number of elements involved.

## Project Components

- **Code**: The generative code for creating artwork using random rectangles, color palettes, and background color selection.
- **Rarity Calculation**: Each generated piece has a rarity score based on the number of rectangles and colors used in the artwork.
- **Math**: We calculate the total number of combinations possible using the provided parameters and color palettes.

## The Code

The code is written in **Processing**. Here's an overview of the key variables involved:

### Color Palettes

- **Base Colors**: 13 colors.
- **Rarity**: The more colors in the palette, the rarer the artwork.

### Generative Art Variables

- **numRects**: The number of rectangles drawn (between 100 and 5000).
- **maxRectLength**: The maximum size of rectangles (between 50 and 400).
- **minRectLength**: The minimum size of rectangles (between 100 and 400).
- **rectWidth**: Width of the rectangles (between 10 and 50).

### Rarity Calculation

The rarity score is determined by the number of rectangles drawn. Here's a mapping for rarity:

- Less than 1000 rectangles: Common
- 1000 - 2000 rectangles: Uncommon
- 2000 - 3000 rectangles: Rare
- 3000 - 4000 rectangles: Very Rare
- More than 4000 rectangles: Legendary

### Math Behind the Combinations

We calculate the total number of possible combinations based on the number of colors (1 to 13) used in the palette and other variables.

#### Formula for Combinations:
The total combinations are given by:

Total combinations = Σ (Combinations of color palettes) × numRects × maxRectLength × minRectLength × rectWidth × backgroundColor

#### Color Palette Combinations:
The combinations for each number of colors in the palette are calculated using the binomial coefficient, \(\binom{13}{n}\), for \(n = 1\) to \(n = 13\).

\binom{13}{1} = 13 \binom{13}{2} = 78 ... \binom{13}{13} = 1

### Example:

Let’s break it down for the case of \(n = 1\):

- **1 color palette (common)**: There are 13 ways to choose 1 color.
- Then we multiply this by the total combinations of other variables: numRects, maxRectLength, minRectLength, rectWidth, backgroundColor.

#### Calculation:
For \(n = 1\), the total combinations would be:

Combinations = 13 × 4901 × 351 × 301 × 41 × 13

We can compute this for all values of \(n\) and get the total number of combinations.

## Getting Started

To run this project:

1. Download and install **Processing** from [processing.org](https://processing.org/download/).
2. Clone or download this repository.
3. Open the `Lo.pde` file in Processing.
4. Run the sketch to generate random art pieces.

## License

This project is licensed under the **CC04** license.


