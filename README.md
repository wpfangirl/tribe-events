# tribe-events
## Events Calendar and Events Calendar Pro files from the KiaMiller.com website

These files are meant to be companions to the <a href="https://www.wpfangirl.com/series/modern-tribe-tutorials/">tutorials on my wpfangirl.com site</a> about modifying Modern Tribe's <a href="https://theeventscalendar.com/product/wordpress-events-calendar-pro/">Events Calendar Pro</a> plugin on <a href="https://www.kiamiller.com">Kia Miller's Radiant Body Yoga site</a>. You can see them in action at https://www.kiamiller.com/events.

Note that the code snippets in the tutorials may not match these files exactly, because I tend to write new tutorials rather than updating old ones. Compare the date the file was uploaded to the date the tutorial written to be sure which is newer, as I haven't automated the process of updating these. 

Also note that if/when I get around to creating a completely new view based on CSS Grid, I will probably create a new repo for that.

## What's What

Not all files are used for all tutorials, so I thought it would be helpful to let you know which files and folders in this repo apply to which Events Calendar views or widgets.

### `default-template.php`

If you don't use the <a href="https://www.studiopress.com/features/">Genesis Theme Framework</a>, you don't need this file. What it does is sets the page layout for events to full-width, removes the normal Genesis loop, and adds the Events Calendar content, taken from the `default-template.php` file in the plugin folder. If you do use a Genesis theme, you'll want something like this to make sure that event pages are compatible with Genesis. In some cases, if you use a different framework, you might need to make different modifications to the default event template. *But if you're not using Genesis, ignore this file.*

### `tribe-events.css`

This is where Modern Tribe wants you to overwrite any CSS that's used in The Events Calendar (the free version). There are two more CSS files inside the `pro` folder. This is frankly rather annoying, and what I've ended up doing is putting my Tribe Events CSS (and other CSS that needs to override plugin CSS) into an entirely different Custom CSS file that loads after the plugin CSS does. I understand why Modern Tribe set it up this way, but it's a pain to maintain all those files. Most of the styles in here affect the single event template. 

### `single-event.php`

This file has been modified to show additional pricing info (a custom field created with ACF) and a button that links to the ticket purchase or application form. *If you are only interested in changing the photo view or the widget, you can ignore this file.*

### `modules/meta/details.php`

Adds additional price information to the single event page. Removes event category and tag display from single event page (requested by client). 

### `pro`

This folder contains the files for modifying anything in Events Calendar Pro (widgets & photo view).

#### `related-events.php`

Sets thumbnail size for related events to `event-thumbnail`.

#### `tribe-events-pro.css`

Modifies the styles for the related events on the single tribe event, and for the Photo View (this is where we set the event boxes to equal heights).

#### `widget-calendar.css`

Flexbox styles for the horizontal widget, plus some styling for the vertical widget in the sidebar

#### `pro/widgets/`

Files for modifying the advanced list widget that ships with Events Calendar Pro. 

##### `pro/widgets/list-widget.php`
Adds a container div around the events to make it possible to use Flexbox or CSS Grid to display them. 

##### `pro/widgets/modules/single-event.php`

Removes large list date display. Adds additional price information.

### `pro/photo/`
Files for modifying the photo view in Events Calendar Pro.

#### `pro/photo/single-event.php`

Modifies image size to `event-thumbnail`. Removes content/excerpt. Add venue, city, region, and country.
