---
title: Badge
sidebar_label: Badge
slug: badge
---

A Material Design "badge".

Badges are used to show notifications, counts, or status information about its [child](badge#content), typically an icon that is a part of a NavigationBar or a NavigationRail destination or a button's icon.

The information is shown as [`text`](badge#text) on a badge's label. If the `text` is not provided, the badge is shown as a filled circle of [`small_size`](badge#small_size) diameter.

If `text` is provided, the label is a StadiumBorder shaped badge with height equal to [`large_size`](badge#large-size).

import Tabs from '@theme/Tabs';
import TabItem from '@theme/TabItem';

## Examples

[Live example](https://flet-controls-gallery.fly.dev/displays/badge)

### Badge decorating an icon on a NavigationBar

<Tabs groupId="language">
  <TabItem value="python" label="Python" default>

```python
import flet as ft

def main(page: ft.Page):
    page.title = "Badge on a NavigationBar destination icon"
    page.navigation_bar = ft.NavigationBar(
        destinations=[
            ft.NavigationDestination(
                icon_content=ft.Badge(
                    content=ft.Icon(ft.icons.EXPLORE),
                    small_size=10,
                ),
                label="Explore",
            ),
            ft.NavigationDestination(icon=ft.icons.COMMUTE, label="Commute"),
            ft.NavigationDestination(
                icon_content=ft.Badge(content=ft.Icon(ft.icons.PHONE), text="10")
            ),
        ]
    )
    page.add(ft.Text("Body!"))


ft.app(target=main)
```
  </TabItem>
</Tabs>

<img src="/img/docs/controls/badge/badge-navigation-bar.png" className="screenshot-50" />

## Properties

### `alignment`

Aligns the label relative to the content of the badge. 

The alignment positions the label in similar way content of a container is positioned using its [`alignment`](container#alignment), except that, the badge alignment is resolved as if the label was a [`large_size`](badge#large_size) square and `offset` is added to the result.

This value is only used if `text` property is provided.

For example:

```python
badge.alignment = ft.alignment.top_left
```
### `bgcolor`

Background [color](/docs/guides/python/colors) of the label.

### `content`

A child Control contained by the badge, typically an icon that's part of a [`NavigationBar`](navigationbar) or a [`NavigationRail`](navigationrail) destination.

### `label_visible`

If False, label is not displayed. By default, `label_visible` is True. It can be used to create a badge that's only shown under certain conditions.

### `large_size`

The badge's label height if `text` is provided.

Default value is 16. If the default value is overridden then it may be useful to also override `padding` and `alignment`.

### `offset`

Combined with `alignment` to determine the location of the label relative to the content.

This value is only used if `text` is provided.

See Controls [`offset`](/docs/controls#offset) for possible values.

### `padding`

The padding added to the badge's label.

This value is only used if `text` is provided. Defaults to 4 pixels on the left and right.

See Container's [`padding`](container/#padding) for possible values.

### `small_size`

The badge's label diameter if `text` is not provided.

Default value is 6.

### `text`

The text shown on badge's label, typically 1 to 4 characters.

If the text is not provided, the badge is shown as a filled circle of [`small_size`](badge#small_size) diameter. 

If `text` is provided, the label is a StadiumBorder shaped badge with height equal to [`large_size`](badge#large-size).

### `text_color`

[Color](/docs/guides/python/colors) of the text shown in the label. This color overrides the color of the label's `text_style`.

### `text_style`

The text style to use for text in the label. See [`text_style` properties](text#textstyle-properties) for possible values.



