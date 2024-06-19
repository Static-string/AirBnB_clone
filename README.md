0x00. AirBnB clone - The console
-> Introduction
    The AirBnB project is a clone web application development.
    The 0x00 project focuses on the backend development of the console.

    In this project the follwoing will be done: 
    * Create a new object 
    * Retrieve an object from a file, a database etc… 
    * Do operations on objects 
    * Update attributes of an object
    * Destroy an object 

-> The console 
    The console is a command interpreter which reads, interprets and executes
    commands through a command line interpreter. It uses a base class for 
    command processes.

    The console can be used to (commands): 

    * Create new instances of a given class
      $ create <class>

      (hbnb) create BaseModel
      49faff9a-6318-451f-87b6-910505c55907 
      (hbnb) all BaseModel

    * Destroy a class instance (based on a class ID)
      $ destroy <class><id>

      (hbnb) destroy BaseModel 49faff9a-6318-451f-87b6-910505c55907
      (hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
      ** no instance found **
      (hbnb)

    * Print the string representation of a class instance (based on class id)
      $ show <class><id>

      (hbnb) show BaseModel 49faff9a-6318-451f-87b6-910505c55907
      [BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293), 
      'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}

    * Print the string representation of all classes
      $ all <class>

      (hbnb) all BaseModel
      ["[BaseModel] (49faff9a-6318-451f-87b6-910505c55907) {'created_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903293),
      'id': '49faff9a-6318-451f-87b6-910505c55907', 'updated_at': datetime.datetime(2017, 10, 2, 3, 10, 25, 903300)}"]

    * Counts the number of instances of a given class
      $ count <class>

      (hbnb) User.count()
      2
      (hbnb) User.destroy("246c227a-d5c1-403d-9bc7-6a47bb9f0f68")
      (hbnb) User.count()
      1
      (hbnb) User.destroy("Bar")
      ** no instance found **
      (hbnb)

    * Updates the class instance of a given ID
      $update <class><id><attribute name>"<attribute value>"

      (hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
      [User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'first_name': 'Betty', 'last_name': 'Bar',
      'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848291),
      'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
      (hbnb)
      (hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "first_name", "John")
      (hbnb) User.update("38f22813-2753-4d42-b37c-57a17f1e4f88", "age", 89)
      (hbnb)
      (hbnb) User.show("38f22813-2753-4d42-b37c-57a17f1e4f88")
      [User] (38f22813-2753-4d42-b37c-57a17f1e4f88) {'age': 89, 'first_name': 'John', 'last_name': 'Bar',
      'created_at': datetime.datetime(2017, 9, 28, 21, 11, 42, 848279), 'updated_at': datetime.datetime(2017, 9, 28, 21, 15, 32, 299055),
      'password': 'b9be11166d72e9e3ae7fd407165e4bd2', 'email': 'airbnb@mail.com', 'id': '38f22813-2753-4d42-b37c-57a17f1e4f88'}
      (hbnb)

-> Execution

Your shell should work like this in interactive mode:
$ ./console.py
(hbnb) help

Documented commands (type help <topic>):
========================================
EOF  help  quit

(hbnb) 
(hbnb) 
(hbnb) quit
$

But also in non-interactive mode: (like the Shell project in C)
$ echo "help" | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$
$ cat test_help
help
$
$ cat test_help | ./console.py
(hbnb)

Documented commands (type help <topic>):
========================================
EOF  help  quit
(hbnb) 
$

-> Storage
  The class FileStorage instance storage object is used to update file json data.
  Everytime a class instance is created, updated or deleted the storage object is called to play.

-> Starting and closing the console

  * To start the console:
    $ ./console.py

  * To quite the console:
    $ quit
