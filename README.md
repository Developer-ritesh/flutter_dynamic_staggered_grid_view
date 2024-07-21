# flutter_dynamic_staggered_grid_view

`flutter_dynamic_staggered_grid_view` is a Flutter package for creating staggered grid layouts, making it easy to build beautiful and responsive grid designs. This package offers advanced features like customizable grid layouts, flexible item sizes, and easy integration with other Flutter widgets.

## Features

- Customizable staggered grid layouts
- Flexible item sizes
- Easy integration with other Flutter widgets
- Smooth scrolling and performance optimization
- Support for both vertical and horizontal grids

## Installation

Add `flutter_dynamic_staggered_grid_view` to your `pubspec.yaml` file:

```yaml
dependencies:
  flutter_dynamic_staggered_grid_view: ^1.0.0
```

Then, run flutter pub get to fetch the package.

## Usage

- Import the package

```dart
import 'package:flutter_dynamic_staggered_grid_view/flutter_dynamic_staggered_grid_view.dart';
```

### Basic Usage Example
```dart
import 'package:flutter/material.dart';
import 'package:flutter_dynamic_staggered_grid_view/flutter_dynamic_staggered_grid_view.dart';

void main() => runApp(MyApp());

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Staggered Grid Example')),
        body: Padding(
          padding: const EdgeInsets.all(8.0),
          child: StaggeredGrid.count(
            crossAxisCount: 4,
            mainAxisSpacing: 4.0,
            crossAxisSpacing: 4.0,
            children: List.generate(20, (index) {
              return Container(
                color: Colors.teal[100 * (index % 9)],
                height: (index % 7 + 1) * 100,
                child: Center(child: Text('Tile $index')),
              );
            }),
          ),
        ),
      ),
    );
  }
}
```
### Customizing the Grid

You can customize the grid by specifying the crossAxisCount, mainAxisSpacing, and crossAxisSpacing properties:

```dart
StaggeredGrid.count(
  crossAxisCount: 4,
  mainAxisSpacing: 8.0,
  crossAxisSpacing: 8.0,
  children: List.generate(20, (index) {
    return Container(
      color: Colors.blue[100 * (index % 9)],
      height: (index % 5 + 1) * 100,
      child: Center(child: Text('Tile $index')),
    );
  }),
)
```

### GridView Builder

The StaggeredGridView.countBuilder is a powerful and flexible way to create staggered grid layouts. It allows you to dynamically build grid items and customize their appearance and behavior. Here's an example:

```dart
StaggeredGridView.countBuilder(
  physics: NeverScrollableScrollPhysics(),
  shrinkWrap: true,
  crossAxisCount: 2,
  itemCount: 4,
  itemBuilder: (context, index) => Container(
    height: 200 * index.toDouble(),
    color: Colors.blue,
    child: Center(child: Text('Item $index')),
  ),
  staggeredTileBuilder: (index) => StaggeredTile.fit(1),
  mainAxisSpacing: 10.0,
  crossAxisSpacing: 10.0,
)
``` 

- `physics:` Controls the scroll behavior of the grid. Setting it to NeverScrollableScrollPhysics() - `makes the` grid non-scrollable.
- `shrinkWrap:` If set to true, it reduces the size of the grid to fit the content. This is useful - `when the` grid is used inside another scrollable widget.
- `crossAxisCount:` Defines the number of columns in the grid.
- `itemCount:` Specifies the number of items in the grid.
- `itemBuilder:` Builds the grid items dynamically. Here, each item is a Container with a height - `proportional to` its index.
- `staggeredTileBuilder:` Defines the layout of each tile. In this example, each tile takes up one - `column.`
- `mainAxisSpacing and` crossAxisSpacing: Define the spacing between the tiles.


## Contributing

Contributions are welcome! Please open an issue or submit a pull request on GitHub.

## License
 
This project is licensed under the MIT License. See the LICENSE file for details.

```
Feel free to adjust the content and formatting as needed.
```

# GitHub
For more details, [visit the GitHub repository](https://github.com/Developer-ritesh/flutter_dynamic_staggered_grid_view)

Official Website : [BihariGraphic](https://biharigraphic.com/)

Copyright (c) 2024 [Developer Ritesh](https://www.google.com/search?q=Developer+Ritesh)