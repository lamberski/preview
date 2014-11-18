# Preview

Preview is simple PHP tool for showing web project to the client. Thanks to various types of content presentation, it can be also used to show preview of mobile designs in tablet or phone.

![](screenshot.png)

## Usage

To add or modify sections to index page, use `config.php` file located in root directory.

```php
<?php

return [
  'name' => 'Project Name',
  'sections' => [
    [
      'name' => 'Section Name',
      'layout' => 'columns',
      'items' => [
        [
          'name' => 'Item Name',
          'description' => '',
          'type' => 'file',
          'url' => '',
          'icon' => '',
          'class' => 'done',
        ],
      ],
    ],
  ],
];
```

## Options

There is number of options to configure look and content of index page.

### Global

<table>
  <thead>
    <tr>
      <th>Property</th>
      <th>Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row"><code>name</code></th>
      <td><code>""</code></td>
      <td><code>String</code> Project name displayed at the top of index page.</td>
    </tr>
    <tr>
      <th scope="row"><code>sections</code></th>
      <td><code>[]</code></td>
      <td><code>Array</code> Array of sections containing items.</td>
    </tr>
  </tbody>
</table>

### Section

<table>
  <thead>
    <tr>
      <th>Property</th>
      <th>Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row"><code>name</code></th>
      <td><code>""</code></td>
      <td><code>String</code> Name of the section.</td>
    </tr>
    <tr>
      <th scope="row"><code>description</code></th>
      <td><code>""</code></td>
      <td><code>String</code> Optional description for the item.</td>
    </tr>
    <tr>
      <th scope="row"><code>layout</code></th>
      <td><code>"single"</code></td>
      <td><code>String</code> Accepts: <code>"single"</code> or <code>"split"</code>. Split layout shows two columns with items instead of one.</td>
    </tr>
    <tr>
      <th scope="row"><code>items</code></th>
      <td><code>[]</code></td>
      <td><code>Array</code> Array of items in section.</td>
    </tr>
  </tbody>
</table>

### Item

<table>
  <thead>
    <tr>
      <th>Property</th>
      <th>Default</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th scope="row"><code>name</code></th>
      <td><code>""</code></td>
      <td><code>String</code> Name of the item.</td>
    </tr>
    <tr>
      <th scope="row"><code>type</code></th>
      <td><code>"link"</code></td>
      <td><code>String</code> Accepts: <code>"link"</code>,  <code>"tablet"</code>,  <code>"iphone"</code> or <code>"design"</code>.</td>
    </tr>
    <tr>
      <th scope="row"><code>url</code></th>
      <td><code>""</code></td>
      <td><code>String</code> Link or relative path to the resouce.</td>
    </tr>
    <tr>
      <th scope="row"><code>icon</code></th>
      <td><code>"file-o"</code></td>
      <td><code>String</code> Name of one of <a href="http://fontawesome.io/icons/">Font Awesome</a> icons (should be entered without <code>fa-</code> prefix). If <code>false</code>, icon is not displayed at all.</td>
    </tr>
    <tr>
      <th scope="row"><code>class</code></th>
      <td><code>""</code></td>
      <td><code>String</code> CSS class added to item. Available classes: <code>"done"</code> (only this one for now).</td>
    </tr>
  </tbody>
</table>

## Example configuration

Below is example config.php file. The same data was used in screenshot at the top of `readme.md`.

```php
<?php

return [
  'name' => 'Project Name',
  'sections' => [
    [
      'name' => 'Designs',
      'layout' => 'split',
      'items' => [
        [
          'name' => 'Home',
          'url' => '#',
          'type' => 'tablet',
          'class' => 'done',
        ],
        [
          'name' => 'About',
          'url' => '#',
          'class' => 'done',
        ],
        // ...
        [
          'name' => 'Registration',
          'url' => '#',
          'type' => 'phone',
          'class' => 'done',
        ],
        [
          'name' => 'Log in',
          'url' => '#',
        ],
      ],
    ],
    [
      'name' => 'Attachments',
      'items' => [
        [
          'name' => 'PSD + PNG files',
          'url' => '#',
          'type' => 'link',
          'icon' => 'file-zip-o',
          'class' => 'done',
        ],
      ],
    ],
  ],
];
```

## Changes in styling

Sass is used to generate CSS style. If you want to modify look of Preview, run below command after applying changes to `main.scss` file.

```
sass main.scss:main.css --style compressed
```

## Deployment

You can easily deploy preview with all the files via (S)FTP using [dploy](https://github.com/LeanMeanFightingMachine/dploy). In root directory of the project, there's `dploy.yaml` file with basic configuration already being added. Just add your remot directory, host, user and password info and you're ready to go!

```
deploy
```

For more info, check out [dploy](https://github.com/LeanMeanFightingMachine/dploy) project page.
