# gdsc-flutter-class-2

## Creating a Calculator in flutter
- Create a flutter project named **flutter_calculator** as explained [earlier](https://github.com/rahulmokaria/gdsc-flutter-class-1) 
- A simple counter project is created as default.
- Since our aim does not involve any functoinality of this we will remove this code.
- So, in main.dart file of lib directory, we remove the code which is of no use to us i.e. from **Line 32**(remove the following code).
```

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  // This widget is the home page of your application. It is stateful, meaning
  // that it has a State object (defined below) that contains fields that affect
  // how it looks.

  // This class is the configuration for the state. It holds the values (in this
  // case the title) provided by the parent (in this case the App widget) and
  // used by the build method of the State. Fields in a Widget subclass are
  // always marked "final".

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
  int _counter = 0;

  void _incrementCounter() {
    setState(() {
      // This call to setState tells the Flutter framework that something has
      // changed in this State, which causes it to rerun the build method below
      // so that the display can reflect the updated values. If we changed
      // _counter without calling setState(), then the build method would not be
      // called again, and so nothing would appear to happen.
      _counter++;
    });
  }

  @override
  Widget build(BuildContext context) {
    // This method is rerun every time setState is called, for instance as done
    // by the _incrementCounter method above.
    //
    // The Flutter framework has been optimized to make rerunning build methods
    // fast, so that you can just rebuild anything that needs updating rather
    // than having to individually change instances of widgets.
    return Scaffold(
      appBar: AppBar(
        // Here we take the value from the MyHomePage object that was created by
        // the App.build method, and use it to set our appbar title.
        title: Text(widget.title),
      ),
      body: Center(
        // Center is a layout widget. It takes a single child and positions it
        // in the middle of the parent.
        child: Column(
          // Column is also a layout widget. It takes a list of children and
          // arranges them vertically. By default, it sizes itself to fit its
          // children horizontally, and tries to be as tall as its parent.
          //
          // Invoke "debug painting" (press "p" in the console, choose the
          // "Toggle Debug Paint" action from the Flutter Inspector in Android
          // Studio, or the "Toggle Debug Paint" command in Visual Studio Code)
          // to see the wireframe for each widget.
          //
          // Column has various properties to control how it sizes itself and
          // how it positions its children. Here we use mainAxisAlignment to
          // center the children vertically; the main axis here is the vertical
          // axis because Columns are vertical (the cross axis would be
          // horizontal).
          mainAxisAlignment: MainAxisAlignment.center,
          children: <Widget>[
            const Text(
              'You have pushed the button this many times:',
            ),
            Text(
              '$_counter',
              style: Theme.of(context).textTheme.headlineMedium,
            ),
          ],
        ),
      ),
      floatingActionButton: FloatingActionButton(
        onPressed: _incrementCounter,
        tooltip: 'Increment',
        child: const Icon(Icons.add),
      ), // This trailing comma makes auto-formatting nicer for build methods.
    );
  }
}
```
- Now we will create the file for our calculator screen, for which we will create a new file in lib folder named **calc.dart**.
- In the new file, we will create a stateful widget as our screen will have values that change.
- For that just type **stf** and from the options available choose flutter stateful widget.
![image](https://user-images.githubusercontent.com/76885050/228467152-c32c8065-795a-42e3-a7cd-d3b14278c080.png)
- Name this widget **CalcPage**, we are left with the following code in calc.dart
```
import 'package:flutter/src/widgets/framework.dart';
import 'package:flutter/src/widgets/placeholder.dart';

class CalcPage extends StatefulWidget {
  const CalcPage({super.key});

  @override
  State<CalcPage> createState() => _CalcPageState();
}

class _CalcPageState extends State<CalcPage> {
  @override
  Widget build(BuildContext context) {
    return const Placeholder();
  }
}
```
- Now we change the page loaded when our app opens with changing **Line 27** in main.dart.
```
      home: const CalcPage(),
```
- Now we will create the front end part(UI) of our app.
- For that we use Scaffold widget wrapped with SafeArea to be returned from CalcPage at **Line 14**
```
    return SafeArea();
```
- Adding Scaffold widget as a child of SafeArea:
```
return SafeArea(
      child: Scaffold(),
    );
```

The Scaffold() widget has properties like appBar, body, floating action button etc. So here we will be making use of the appBar and body properties. The appBar property is where we provide the title and other actions in our app. The app bar is quite simple with a background colour and a text
- Now we will create an app bar for our application by adding appBar attribute to our Scaffold .
```
child: Scaffold(
        appBar: AppBar(),
      ),
```
- In the AppBar widget, we give the title attribute a Text widget widget with name **Calculator**.
```
appBar: AppBar(
          title: Text("Calculator"),
        ),
```
In AppBar() widget we can provide the background color, title and center title properties as bel

