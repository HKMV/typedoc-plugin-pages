## Overview

Page groups can be used to group collections of pages that are related to one another.

Each page group and its member pages will be displayed as a group of navigation items in the navigation sidebar.

## When to use page groups

Page groups should be used to group related pages in two scenarios:

### 1. Top-level page content

All top-level pages are organized into groups. You may have as few as one groups defined.

### 2. Page sections

To avoid overcrowding the navigation sidebar, groups can also be split up into sections. Page sections serve as a collection of page groups.

See {@page Page Sections} for more information.

## Creating Groups

Follow these steps to create a page group:

1. Create a JSON definition for the group:

```json
{
	"title": "My Group",
	"pages": []
}
```

2. Add the group definition JSON to either:

- The top-level `groups` array
- The `groups` array of a page section

## Group Options

In addition to the required `title` and `pages` properties, page groups definitions support two optional properties:

### 1. Output

The optional `output` property supports configuring the name of the directory that pages within the group are rendered to.

> 👉 For example, the following page definiton would be rendered to `my-group/my-page.html`:

```json
{
	"groups": [
		{
			"title": "My Group",
			"output": "my-group",
			"pages": [
				{
					"title": "My Page",
					"source": "my-page.md",
					"output": "my-page.html"
				}
			]
		}
	]
}
```

If no `output` property is provided, the group's title will be used as the default value.

### 2. Source

The optional `source` property allows you to configure a default path prefix for the `source` property of each page within the group.

> 👉 For example, the following page would be read from `my-group/my-page.md`:

```json
{
	"groups": [
		{
			"title": "My Group",
			"source": "my-group",
			"pages": [
				{
					"title": "My Page",
					"source": "my-page.md",
				}
			]
		}
	]
}
```

By default, no source path prefix is applied when the `source` property is omitted.