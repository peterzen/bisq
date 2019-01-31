
## CSS framework

### Colors

[_variables.scss](_variables.scss) - The global color palette is defined here using SASS variables.  This is the file to set the colors that are reused across the application in order to ensure consistency - ideally, no other CSS files contains direct color reference.

[_base-colors.scss](_base-colors.scss) - this is the file that defines the color palette that is independent of the theme (light or dark) being used, in the form of CSS variables that are then referenced from the styles that define the UI look and feel. Colors that are reused across themes are best defined here in order to avoid duplication in the theme CSS.

[theme-light.scss](theme-light.scss) and [theme-dark.scss](theme-dark.scss) define the theme dependent colors, referencing the variables defined in the above files.

[_*.scss]() - SASS modules that contain the styles for various components and views.  In terms of colors, these should reference the CSS variables defined in `_base-colors.scss` and `theme-*.scss` so that the UI can be easily re-colored without touching these files.


[bisq.scss](bisq.scss) is the top level SASS file that includes the base colors and all of the SASS modules.  The compiled `bisq.css` is loaded in `BisqApp.java`, in addition to `theme-*.css`.

### Adding new UI themes

Themes are defined in [UITheme.java](../../../../src/main/java/bisq/desktop/util/UITheme.java
), this is the list the `ComboBox` in the Preferences panel is populated from.
