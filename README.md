<h1 id="header" align="center">
ScrollbarUltima
</h1>
<div id="header" align="center">
Powerful Flutter package that allows you to create highly customizable scrollbars!
</div>

## Try It!

### Default

<img src="https://github.com/C0ntrolDev/scrollbar_ultima/blob/main/docs/images/default_example.gif" width="400" />

```dart
@override
Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(title: const Center(child: Text("Default Example"))),
    body: SafeArea(
      child: ScrollbarUltima(
        child: ListView.builder(itemCount: 100, itemBuilder: _buildItem),
      ),
    ),
  );
}

Widget _buildItem(BuildContext context, int index) {
  return ListTile(
    title: Text("Title of $index item"),
    subtitle: Text("Subtitle of $index item"),
    trailing: const Text("^_^"),
  );
}
```

### Semicircle with Item index precalculation

<img src="https://github.com/C0ntrolDev/scrollbar_ultima/blob/main/docs/images/semicircle_example.gif" width="400" />

```dart
@override
Widget build(BuildContext context) {
  return Scaffold(
    appBar: AppBar(title: const Center(child: Text("Semicircle Example"))),
    body: SafeArea(
      child: ScrollbarUltima.semicircle(
        labelContentBuilder: (offset, index) => Padding(
            padding: const EdgeInsets.symmetric(vertical: 3, horizontal: 5),
            child: Text(
              index.toString(),
              style: const TextStyle(color: Colors.grey),
            )),
        precalculateItemByOffset: true,
        prototypeItem: _buildItem(context, 0),
        child: ListView.builder(itemCount: 100, itemBuilder: _buildItem),
      ),
    ),
  );
}

Widget _buildItem(BuildContext context, int index) {
  return ListTile(
    title: Text("Title of $index item"),
    subtitle: Text("Subtitle of $index item"),
    trailing: const Text("^_^"),
  );
}
```

### Customized

<img src="https://github.com/C0ntrolDev/scrollbar_ultima/blob/main/docs/images/customized_example.gif" width="400" />

```dart
@override
Widget build(BuildContext context) {
  return Scaffold(
    body: ScrollbarUltima.semicircle(
      backgroundColor: Theme.of(context).colorScheme.surfaceContainerHighest,
      arrowsColor: Theme.of(context).colorScheme.onSurface,
      labelBehaviour: LabelBehaviour.showOnlyWhileAndAfterDragging,
      labelContentBuilder: (offset, index) => Padding(
        padding: const EdgeInsets.symmetric(vertical: 8, horizontal: 10),
        child: Text(index.toString()),
      ),
      isFixedScroll: true,
      precalculateItemByOffset: true,
      alwaysShowThumb: false,
      prototypeItem: _buildItem(context, 0),
      hideThumbWhenOutOfOffset: true,
      minScrollOffset: 200 - 70,
      itemPrecalculationOffset: 200 - 70,
      scrollbarPadding: EdgeInsets.only(top: MediaQuery.of(context).viewPadding.vertical + 70),
      child: CustomScrollView(
        slivers: [
          const SliverAppBar(
              forceElevated: true,
              pinned: true,
              expandedHeight: 200,
              collapsedHeight: 70,
              flexibleSpace: FlexibleSpaceBar(title: Text("Customized Example"))),
          SliverList.builder(itemCount: 100, itemBuilder: _buildItem),
        ],
      ),
    ),
  );
}

Widget _buildItem(BuildContext context, int index) {
  return ListTile(
    title: Text("Title of $index item"),
    subtitle: Text("Subtitle of $index item"),
    trailing: const Text("^_^"),
  );
}
```

## Features

- 🎨 **Fully Customizable Label, Thumb, Track** - Modify the appearance of label, thumb, and track.
- 🔄 **Various Label and Track Behaviors** - Implement different behaviors for labels and tracks.
- 📏 **Scrollable Area Specification** - Define the scrollable area for precise control.
- 📌 **Fixed Scroll Mode** - Scrolling is done element by element, which allows for smooth scrolling in large lists.
- 🔍 **Element Index Prediction** - Predict the index of elements for label displaying.
- 🖥️ **Various Screen Positions** - Place scrollbars at different positions on the screen.
- 🧩 **Seamless Integration with CustomScrollView** - Easily work with CustomScrollView for advanced scrolling effects.

## Basic docs

TODO

## Additional information

- 📚 More examples can be found in the **examples** folder
- ⭐ I would appreciate it if you **star this repository!**

<h3 id="header" align="center">
^_^
</h3>
