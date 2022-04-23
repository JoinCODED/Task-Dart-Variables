1. Start by defining your main function:

```dart
void main() {
}
```

2. Let's define our first variable which is `firstName` of type `String`.

```dart
void main() {
    String firstName = "John";
}
```

3. `lastName` is a `String` as well:

```dart
void main() {
    String firstName = "John";
    String lastName = "Doe";
}
```

4. `age` is a number, so we have to define it with `int`:

```dart
void main() {
    String firstName = "John";
    String lastName = "Doe";
    int age = 24;
}
```

5. And lastly, `height` is a number as well but with decimal places so we will define it with `double`:

```dart
void main() {
    String firstName = "John";
    String lastName = "Doe";
    int age = 24;
    double height = 1.78;
}
```

6. Now use `print` to print your variables one by one to the console:

```dart
void main() {
    String firstName = "John";
    String lastName = "Doe";
    int age = 24;
    double height = 1.78;

    print(firstName);
    print(lastName);
    print(age);
    print(height);
}
```

### 🍋 booleans

1. Create a variable called `married` of type boolean:

```dart
void main() {
    String firstName = "John";
    String lastName = "Doe";
    int age = 24;
    double height = 1.78;
    bool married = false;
    print(firstName);
    print(lastName);
    print(age);
    print(height);
}
```

2. Print it to the console:

```dart
void main() {
    String firstName = "John";
    String lastName = "Doe";
    int age = 24;
    double height = 1.78;
    bool married = false;
    print(firstName);
    print(lastName);
    print(age);
    print(height);
    print(married);
}
```

# String Interpolation ➕

1. In your main function we have the following variables:

```dart
void main() {
double temperature = 20;
String drink = 'juice';
String flavor = 'orange';
}
```

2. Let's print the first variable `temperature`:

```dart
void main() {
double temperature = 20;
String drink = 'juice';
String flavor = 'orange';

print("The temperature is C");
}
```

3. As you learned you have 2 ways of interpolating strings, let's try them both:

```dart
print("The temperature is $temperatureC");
```

Using only the dollar sign to inject the variable will cause the compiler to get confused and think that `temperatureC` is a whole word and will look for a variable with this name.

The solution is to use curly braces `{}`:

```dart
print("The temperature is ${temperature}C");
```

4. Let's print our second statement:

```dart
void main() {
double temperature = 20;
String drink = 'juice';
String flavor = 'orange';

print("The temperature is ${temperature}C");
print("I like $flavor $drink.");
}
```

### 🍋 Arithmetic spice

1. Create a variable named `number` of type `int`:

```dart
void main() {
double temperature = 20;
String juice = 'juice';
String flavor = 'orange';
int number = 5;

print("The temperature is ${temperature}C");
print("I like $flavor $juice.");
}
```

2. Print this variable:

```dart
void main() {
double temperature = 20;
String drink = 'juice';
String flavor = 'orange';
int number = 5;

print("The temperature is ${temperature}C");
print("I like $flavor $drink.");
print("$number plus $number makes $number + $number");
}
```

But the output would be:

```
5 plus 5 makes 5 + 5
```

To have an `expression` in a string we also have to use the curly braces `{}` as everything in those curly braces will be evaluated as dart `expression`.

```dart
void main() {
double temperature = 20;
String drink = 'juice';
String flavor = 'orange';
int number = 5;

print("The temperature is ${temperature}C");
print("I like $flavor $drink.");
print("$number plus $number makes ${number + number}");
}
```

# String Methods 🔧

1. Your main method should look like this:

```dart
void main() {
  String fullName = " John doe";
}
```

2. Print out the output using string interpolation:

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName} and my last name length is ${fullName}")
}
```

3. To get only ` John` out of ` John doe` we will use the `subString` method, let's count the starting point and the ending point, we will start from the index `0` and count: white space :0, J :1, o :2, h :3, n :4

And for substring we provide the end point as **To but not including** so the end point would be `5`.

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName.subString(0,5)} and my last name length is ${fullName}")
}
```

output:

```
My name is  John and my last name length is John doe
```

4. Next, we will use the `toUpperCase()` method and chaining:

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName.subString(0,5).toUpperCase()} and my last name length is ${fullName}")
}
```

output:

```
My name is  JOHN and my last name length is John doe
```

5. Now for the last name, we will use `subString()` method again from the index of `6` which is the index of the letter `d` and we won't provide a second argument and that means the end point is the last index of the given string:

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName.subString(0,5).toUpperCase()} and my last name length is ${fullName.subString(6)}")
}
```

output:

```
My name is  JOHN and my last name length is doe
```

6. To get a length of a string we use the `length` method:

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName.subString(0,5).toUpperCase()} and my last name length is ${fullName.subString(6).length}")
}
```

output:

```
My name is  JOHN and my last name length is 3
```

### 🍋 White Spaces

The method we gonna use is the `trim()` method which removes white spaces in the beginning and the end of a string:

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName.subString(0,5).toUpperCase().trim()} and my last name length is ${fullName.subString(6).length}")
}
```

output:

```
My name is JOHN and my last name length is 3
```

### 🌶 Does My Last Name Starts With The Letter d?

The method to use here is `startsWith` method which returns true or false:

```dart
void main() {
  String fullName = " John doe";

  print("My name is ${fullName.subString(0,5).toUpperCase().trim()} and my last name length is ${fullName.subString(6).length}")
  print(fullName.substring(6).startsWith("d"));
}
```

output:

```
My name is JOHN and my last name length is 3
true
```

# Another solution

```dart
void main() {
String fullName = " John doe";
String firstName = fullName.substring(0,5);
String lastName = fullName.substring(6);
print("My name is ${firstName.toUpperCase().trim()} and my last name length is ${lastName.length}");
print(lastName.startsWith("d"));
}
```
