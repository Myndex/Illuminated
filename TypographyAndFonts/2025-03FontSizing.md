# March 11, 2025
https://github.com/w3c/wcag3/issues/266#issuecomment-2712903026

----


# Font Sizing
In reference to Legge et alia, we know that 0.2° is the critical size for best speed, and Whittaker/Lovie-Kitchin presented the concept of "acuity reserve", which also assesses sub-fluent levels, and spot reading.

In terms of cognitive design considerations, the visual hierarchy is important. Everything can not and should not be at a max contrast nor size. There needs to be variation, with most important content (main body text) having the best readability contrast, while some elements such as copyright bug, may be far diminished to reduce visual clutter.

Therefore a practical standard must allow for sub-fluent or spot readable (i.e. with fixation) elements. In the table below, these assume that all items are at the level of "contrast constancy", meaning the font weight and white space, in conjunction with the color pair, are of sufficient contrast that no further contrast increase will improve readability.

This table also assumes the screen resolution/distance is that of the standard CSS reference px, and a font with an x-height ratio of 0.52. So for Helvetica, and a standard distance from a standard screen, we have these relationships:

### VA° x-Height (Helvetica, 0.52 x-Height Ratio)
| VA°   | ArcMin | x-hgt px | font px | font pt |    Class           | Use Case            |
|-------|--------|----------|---------|---------|--------------------|---------------------|
| 0.08° | 5ʹ     | 3.9px    | 7.5px   | 5.6pt   | 20/20 Acuity Limit | Clinical Only       |
| 0.11° | 6.6ʹ   | 5.2px    | 10px    | 7.5pt   | Spot Limit         | Ancillary/minimum   |
| 0.13° | 8ʹ     | 6.2px    | 12px    | 9pt     | Sub-Fluent         | Footer, non-content |
| 0.16° | 9.3ʹ   | 7.3px    | 14px    | 10.5pt  | Sub-Fluent   | Captions |   
| 0.18° | 10.6ʹ  | 8.3px    | 16px    | 12pt    | Critical Size (Fluent)| Content MIN     |
| 0.2°  | 12ʹ    | 9.4px    | 18px    | 13.5pt  | Critical Size (body)| Columns or Blocks  |
| 0.24° | 14ʹ    | 11px     | 21.5px  | 16pt    | Preferred Body     | More Ideal Columns  |
| 0.27° | 16ʹ    | 12.5px   | 24px    | 18pt    | "Large Print"      | (for comparison)    |
| 0.35° | 21ʹ    | 16.6px   | 32px    | 24pt    | Median Vision      | (20/40 fluent)      |
| 0.5°  | 30ʹ    | 23.5px   | 45px    | 34pt    |                    |               |
| 0.7°  | 43ʹ    | 33px     | 64px    | 48pt    | 16px txt Zoom Max | Small text can zoom |
| 1°    | 60ʹ    | 47px     | 90px    | 68pt    |                    |              |
| 1.4°  | 85ʹ    | 67px     | 128px   | 96pt    | 48px txt Zoom Max | Large text can zoom |

Regarding zoom levels, what is needed is not a percentage, rather, small body text (16px) should be able to zoom up to 64px, and large headline text (48px) should be able to zoom up to 96px-128px. Headlines do not need to zoom up nearly as much as small text does.

- For small mobile, 200% equivalent
  - 16px text can zoom to 32px
  - 32px text can zoom to 42px
  - 48px text can remain at 48px
- For large mobile and desktop, 400% equivalent
  - 16px can zoom to 64px
  - 32px text can zoom to 96px
  - 48px text can zoom to 128px

## Another chart we've been testing
In this chart the values are slightly different—this reflects the difference in real world devices, as opposed to the CSS Canvas defined px size. This then asks the question regarding "whose px size is ideal for a reference?"

<img alt="FontSize chart 2023" width="480" src="https://github.com/user-attachments/assets/73c3c4b5-5c12-4952-bb8c-3edfad0ee50f" />

## Visual Angle Math
There is a simple formula for visual angle. To make it easier, here are examples with magic numbers (number rounded in some cases):

### Visual Angle (VA) in degrees:

$VA\degree = \frac{height}{distance} \times \frac{180}{pi}$

or 
```JS
  let degreesVA = (height/distance) * 57.2957795130823;
```

### Visual Angle Minutes of Arc (vaʹ):

$va\prime =  VA\degree \times 60$

or
```JS
  let arcMinutesVA = (height/distance) * 3437.74677;
```

### Visual Angle per CSS Reference px:

$px = \frac{va\prime}{1.278}$

or
```JS
  let px = (height/distance) * 2689.9427;
    // or
  let px = degreesVA * 46.9483568;
    // or
  let px = arcMinutesVA * 0.7824726;

```

### Practical Application

If we assume a common 16" (40cm) reading distance, and a tablet with a 170ppi (67ppcm) dot pitch (340ppi for a 2:1 retina display), the reference px follows the established 1.278ʹ "standard", giving us:

$px = VA\degree \times 46.9483568$

And

$VA\degree = px \times 0.0213$


<details><summary>CLICK HERE more more math examples</summary>
...


And with a font with a 0.52 ratio, the x-height is:

$VA\degree = fontSizepx \times 0.011076$

Because $0.011076 = 0.0213 \times 0.52$

#### x-heights per VA°

$6.24px = 0.13\degree \times 46.9483568$

$8.3px = 0.177\degree \times 46.9483568$

$9.4px = 0.2\degree \times 46.9483568$

$11.3px = 0.24\degree \times 46.9483568$

$12.5px = 0.266\degree \times 46.9483568$

For a font like Helvetica or Arial, which have a 0.52 x-height ratio, the font size is:

$12px = \frac{6.24px}{0.52}$

$16px = \frac{8.3px}{0.52}$

$18px = \frac{9.4px}{0.52}$

$21.7px = \frac{11.3px}{0.52}$

$24px = \frac{12.5px}{0.52}$

...
</details>

Thank you for reading

Andrew Somers
_Director of Research_
_Inclusive Reading Technologies, Inc._
