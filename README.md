# Flutter Web Smooth Scroll

A package to help you provide a smoother and aesthetic scroll feeling. The motivation behind this package is, while using the official Flutter SDK the scrolling experience on web is very jerky and feels laggy to overcome it and provide more quality scrolling this package is developed.

## Installation

Add

   ```
   dependencies:
  web_smooth_scroll: ^latest_version
   ```

to your pubspec.yaml, and run

   ```
   flutter packages get
   ```

in your project's root directory.

## Basic Usage

1. Import it to your project file

   ```
   import 'package:web_smooth_scroll/web_smooth_scroll.dart';
   ```
   
2. Create a Scroll Controller

   ```
   // Controllers
   late ScrollController _scrollController;

   @override
   void initState() {
   // initialize scroll controllers
   _scrollController = ScrollController();

    super.initState();
   }
   ```
   
3. Use the controller with package

   ```
   @override
   Widget build(BuildContext context) {
   return Scaffold(
   appBar: AppBar(
   title: const Text('Web Smooth Scroll'),
   ),
   body: WebSmoothScroll(
   controller: _scrollController,
   child: SingleChildScrollView(
   physics: const NeverScrollableScrollPhysics(),
   controller: _scrollController,
   child: _buildScrollableList(),
   ),
   ),
   );
   }
   ```

WebSmoothScroll can be used with any scrollable widget, just pass the same scroll controller to WebSmoothScroll as well as the scrollable widget. And also specify scroll physics to NeverScrollableScrollPhysics()

   ```
   WebSmoothScroll(
        controller: _scrollController,
        scrollOffset: 60, // additional offset to users scroll input
        animationDuration: 500, // duration of animation of scroll in milliseconds
        curve: Curves.easeInOutCirc, // curve of the animation
        child: SingleChildScrollView(
          physics: const NeverScrollableScrollPhysics(),
          controller: _scrollController,
          child: _buildScrollableList(),
        ),
    ),
   ```


