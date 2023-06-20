# 💡 luminosity.css

<p align="center">
  <img src="https://github.com/MaximeIJ/luminosity-css/assets/5600516/9f024670-3959-48a7-8c63-55f6971a2dde" height=330 align="center" alt="High contrast mini demo of luminosity.css" />
</p>

This repository provides two themable and customizable CSS classes that can add dynamic lighting to your web page. Try out the [demo](https://maximeij.dev/luminosity-css)!

1. `light-effect` is applied to any element you want casting a shadow. It will use css variables you define to calculate the proper directly and size for the shadow given your element's position relative to the light source.
2. `light-source` is applied to the container and will add a gradient based layer to lighten content close to the source and dark content that is further. Note it's not needed for `light-effect` to work and serves to double down on the luminosity effect.

## Usage

### Basic

- Copy [luminosity.css](luminosity.css) into your project.
  - Modify it if you need to, otherwise apply its classes `.light-effect` and `.light-source` as needed.
- Supply required CSS variables if you don't want default.
  - This is particularly important for element position `--lc-x` and `--lc-y`.
  - See [luminosity.css](luminosity.css) for a description of each variable.
- Take a look at the [demo](index.html) for a working example to get started.

### Theming

You can control the colors of both the ambient light source and the element shadows to fine tune to your site's pallet:

- `--lc-light-on` and `--lc-light-off` can be used to customize the color of the filter applied at both ends of the `.light-effect` container gradient.
  - Use color `opacity` to control the intensity of the ambient light filter.
  - Combine custom colors with `--lc-light-z` and `--lc-light-m` to tighten or loosen the beam of light.
  - Remember: `.light-effect` is not needed for directional shadows to work.
- `--lc-shadow-color` can be used to define the color of the shadows cast by the elements with `.light-effect`. You can pass a custom value to adapt to a given pallet your site is working with and control the `opacity`.

### Customizing

You can control the position of the ambient light source as well as attributes to customize the tightness of the beam and the elongation factor of shadows:

- The ambient source light's position can be modified in 4 ways:
  - `--lc-light-x` and `--lc-light-y` can be used to set the 2d coordinates of the center of the light in `%`. These values can be negative or otherwise outside the bounds of the container to give the light a faraway effect.
  - `--lc-light-z` simulates the height of the light source and indirectly the spread of the beam and blurriness of element shadows. It's best kept positive.
  - `--lc-light-m` is a measure of the extent of the light source's filters (both light and dark). It affects the range of the effect in the `.light-source` gradient but not the shadows of the elements.
- `--lc-x` and `--lc-y` **must** be used on elements for directional shadows to work. They can be set at runtime by javascript for elements that are naturally positioned.
- `--lc-shadow-sensitivity` determines the number of `px` the shadow is offset by for each `%` distance the element is from the light source. By default it's set at `0.05px`.
