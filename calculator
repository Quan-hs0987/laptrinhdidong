import 'package:flutter/material.dart';

void main() {
  runApp(MyApp());
}

class MyApp extends StatelessWidget {
  // This widget is the root of your application.
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
        visualDensity: VisualDensity.adaptivePlatformDensity,
      ), // ThemeData
      home: HomePage(),
      debugShowCheckedModeBanner: false,
    ); // MaterialApp
  }
}

class HomePage extends StatefulWidget{
  @override
 _HomePageState createState() => _HomePageState();
}

class _HomePageState extends State<HomePage> {

  var _firstNumber, _secondNumber;
  var _operator;
  var  _result, _displayText = "";
  void btnClicked(String btnText){
    if (btnText == "C"){
      _result = "";
      _displayText = "";
      _firstNumber = 0;
      _secondNumber = 0;
    } else if (btnText == "+" || btnText == "-" || btnText == "*" || btnText == "/"){
      _firstNumber = int.parse(_displayText);
      _result = "";
      _operator = btnText;
    } else if ( btnText == "="){
      _secondNumber = int.parse(_displayText);
      if(_operator == "+"){
        _result = (_firstNumber + _secondNumber).toString();
      } else if (_operator == "-"){
        _result = (_firstNumber - _secondNumber).toString();
      } else if (_operator == "*") {
        _result = (_firstNumber * _secondNumber).toString();
      } else if (_operator == "/") {
        _result = (_firstNumber ~/ _secondNumber).toString();
      }
    } else {
      _result = int.parse(_displayText +btnText).toString();
    }

    setState(() {
      _displayText = _result;
    });
  }



  Widget customOutlineButton(String value, {Color color = Colors.white, Color backgroundColor = Colors.grey}) {
    return OutlinedButton(
      onPressed: ()  => btnClicked(value),
      style: ButtonStyle(
        foregroundColor: MaterialStateProperty.all<Color>(color),
        backgroundColor: MaterialStateProperty.all<Color>(backgroundColor),
        shape: MaterialStateProperty.all<RoundedRectangleBorder>(
          RoundedRectangleBorder(
            borderRadius: BorderRadius.circular(10.0),
            side: BorderSide(color: Colors.grey)
          )
        )
      ),
//       padding: EdgeInsets.all(25),
      child: Text(
        value,
        style: TextStyle(fontSize: 25, color: color),
      ),
    );

  }

  @override
  Widget build(BuildContext context){
    return Scaffold(
      appBar: AppBar(title: Text('Calculator')),
      body: Container(
        child: Column(
          children: [
            Expanded(
              child: Container(
                color: Colors.black,
                alignment: Alignment.bottomRight,
                padding: EdgeInsets.all(10),
                child: Text(
                  _displayText,
                  style: TextStyle(
                    fontSize: 50,
                    fontWeight: FontWeight.w700,
                    color: Colors.white
                  ),
                ),
              ),
            ),
            Row(
              children: [
                Expanded(child: customOutlineButton("7")),
                Expanded(child: customOutlineButton("8")),
                Expanded(child: customOutlineButton("9")),
                Expanded(child: customOutlineButton("+", color: Colors.red, backgroundColor: Colors.orange)),
              ],
            ),
            Row(
              children: [
                Expanded(child: customOutlineButton("4")),
                Expanded(child: customOutlineButton("5")),
                Expanded(child: customOutlineButton("6")),
                Expanded(child: customOutlineButton("-", color: Colors.red, backgroundColor: Colors.orange)),
              ],
            ),
            Row(
              children: [
                Expanded(child: customOutlineButton("1")),
                Expanded(child: customOutlineButton("2")),
                Expanded(child: customOutlineButton("3")),
                Expanded(child: customOutlineButton("*", color: Colors.red, backgroundColor: Colors.orange)),
              ],
            ),
            Row(
              children: [
                Expanded(child: customOutlineButton("C", color: Colors.red, backgroundColor: Colors.orange)),
                Expanded(child: customOutlineButton("0")),
                Expanded(child: customOutlineButton("=", color: Colors.red, backgroundColor: Colors.orange)),
                Expanded(child: customOutlineButton("/", color: Colors.red, backgroundColor: Colors.orange)),
              ],
            ),
          ],
        ),
      ),
    );
  }
}
