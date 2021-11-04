# najmusshakib-vi-er-
day14
import 'package:flutter/material.dart';

void main() => runApp(MyApp());

class MyApp extends StatefulWidget {
  @override
  MyAppState createState()=> MyAppState();
}
class MyAppState extends State<MyApp>{
  TextEditingController emailController=TextEditingController();
  TextEditingController nameController= TextEditingController();
  TextEditingController passwordCintroller= TextEditingController();
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      home: Scaffold(
        appBar: AppBar(title: Text('Text Faild'),),
        body: Padding(
          padding: EdgeInsets.all(20),
          child: Column(
            children:<Widget>[
              Padding(
                padding: EdgeInsets.all(20),
                child: TextField(
                  controller: emailController,
                  decoration: InputDecoration(
                    border: OutlineInputBorder(),
                      labelText:'Email',
                          hintText: 'ex: example@gmaol.com',
                    )
                  ),
                ),
              RaisedButton(
                textColor: Colors.white,
                color: Colors.lightBlue,
                child: Text('Sing In'),
                onPressed: (){
                  return showDialog(
                      context: context,
                      builder: (context){
                        return AlertDialog(
                          title: Text('Alert!!!'),
                          content: Text(emailController.text),
                          actions: [
                            new FlatButton(
                          child: Text('OK'),
                  onPressed:(){
                            Navigator.of(context).pop()
                  }
                            )
                          ],
                        );
                  }
                },
              )
              ],
            ),
          ),
        ),
      );
  }
}
