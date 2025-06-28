import 'package:flutter/material.dart';

void main() {
  runApp(const MyApp());
}

class MyApp extends StatelessWidget {
  const MyApp({super.key});

  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: const MyHomePage(title: 'Flutter Demo Home Page'),
      debugShowCheckedModeBanner: false,
    );
  }
}

class MyHomePage extends StatefulWidget {
  const MyHomePage({super.key, required this.title});

  final String title;

  @override
  State<MyHomePage> createState() => _MyHomePageState();
}

class _MyHomePageState extends State<MyHomePage> {
 // int _counter = 0;

  var no1Controller = TextEditingController();
  var no2Controller = TextEditingController();
  var result = "";
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      appBar: AppBar(
        title: Text(widget.title),
      ),
      body:Container(
        color: Colors.blue.shade100,
        child: Padding(
          padding: const EdgeInsets.all(8.0),
          child: Center(
            child: Column(
              mainAxisAlignment: MainAxisAlignment.center,
              children: [
                TextField(
                  keyboardType: TextInputType.number,
                  controller: no1Controller ,
                ),
                TextField(
                  keyboardType: TextInputType.number,
                  controller: no2Controller,
                ),
                Padding(
                  padding: const EdgeInsets.all(21.0),
                  child: Row(
                    mainAxisAlignment: MainAxisAlignment.spaceAround,
                    children: [
                      ElevatedButton(onPressed: (){
                        var no1 = int.parse(no1Controller.text.toString());
                        var no2 = int.parse(no2Controller.text.toString());
                        var sum = no1+no2;
                        result = "The sum of  $no1 and $no2 is $sum";
                        setState(() {

                        });
                      }, child: Text('add')),


                      ElevatedButton(onPressed: (){
                        var no1 = int.parse(no1Controller.text.toString());
                        var no2 = int.parse(no2Controller.text.toString());
                        var diff = no1-no2;
                        result = "The different between  $no1 and $no2 is $diff";
                        setState(() {

                        });
                      }, child: Text('sub')),


                      ElevatedButton(onPressed: (){
                        var no1 = int.parse(no1Controller.text.toString());
                        var no2 = int.parse(no2Controller.text.toString());
                        var pro = no1*no2;
                        result = "The Product of  $no1 and $no2 is $pro";
                        setState(() {

                        });
                      }, child: Text('mul')),
                      ElevatedButton(onPressed: (){ var no1 = int.parse(no1Controller.text.toString());
                      var no2 = int.parse(no2Controller.text.toString());
                      var div = no1/no2;
                      result = "The div by $no1 and $no2 is $div";
                      setState(() {

                      });}, child: Text('div')),
                    ],
                  ),
                ),

                Padding(
                  padding: EdgeInsets.all(21),
                  child: Text(
                    result,
                    style: TextStyle(fontSize: 25), // lowercase 'fontSize'
                  ),
                )
              ],
            ),
          ),
        ),
      )
    );
  }
}
