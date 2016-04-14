# no-argument-validation
A small library to validate method parameters (you can download it from [nuget](https://www.nuget.org/packages/NoArgumentValidation/)).

- AssertNotNull
- AssertNotNullOrEmpty
- AssertGreaterThan
- AssertGreaterThanOrEquals
- AssertLessThan
- AssertLessThanOrEquals
- AssertInRange

###### AssertNotNull
```
/// <summary>
/// Throw a <see cref="ArgumentNullException"/> if <paramref name="paramValue"/> is null.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertNotNull<T>(T paramValue, string paramName = null);
```
Usage:
```
public void Test(string variable){
  // variable must not be null.
  Argument.AssertNotNull(variable);
  ...
}
```

###### AssertNotNullOrEmpty
```
/// <summary>
/// Throw a <see cref="ArgumentException"/> if <paramref name="paramValue"/> is null or empty.
/// For Non-Nullable types, check if <paramref name="paramValue"/> equals the type default value.
/// For Nullable types, check if <paramref name="paramValue"/>.Value equals the type default value.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertNotNullOrEmpty<T>(T paramValue, string paramName = null);
```
Usage:
```
public void Test(IEnumerable<string> collection){
  // collection must not be empty.
  Argument.AssertNotNullOrEmpty(collection);
  ...
}
```

###### AssertGreaterThan
```
/// <summary>
/// Throw a <see cref="ArgumentOutOfRangeException"/>
/// if <paramref name="paramValue"/> is not greater than <paramref name="minValue"/>.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="minValue">The min value to compare to <paramref name="paramValue"/>.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertGreaterThan<T>(T paramValue, T minValue, string paramName = null) where T : IComparable<T>;
```
Usage:
```
public void Test(double value){
  // value must be grater than 10.
  Argument.AssertGreaterThan(value, 10);
  ...
}
```

###### AssertGreaterThanOrEquals
```
/// <summary>
/// Throw a <see cref="ArgumentOutOfRangeException"/>
/// if <paramref name="paramValue"/> is less than <paramref name="minValue"/>.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="minValue">The min value to compare to <paramref name="paramValue"/>.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertGreaterThanOrEquals<T>(T paramValue, T minValue, string paramName = null) where T : IComparable<T>;
```
Usage:
```
public void Test(double value){
  // value must be grater than or equals to 5.1.
  Argument.AssertGreaterThanOrEquals(value, 5.1);
  ...
}
```

###### AssertLessThan
```
/// <summary>
/// Throw a <see cref="ArgumentOutOfRangeException"/>
/// if <paramref name="paramValue"/> is not less than <paramref name="maxValue"/>.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="maxValue">The max value to compare to <paramref name="paramValue"/>.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertLessThan<T>(T paramValue, T maxValue, string paramName = null) where T : IComparable<T>;
```
Usage:
```
public void Test(double value){
  // value must be less than 10.
  Argument.AssertLessThan(value, 10);
  ...
}
```

###### AssertLessThanOrEquals
```
/// <summary>
/// Throw a <see cref="ArgumentOutOfRangeException"/>
/// if <paramref name="paramValue"/> is greater than <paramref name="maxValue"/>.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="maxValue">The max value to compare to <paramref name="paramValue"/>.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertLessThanOrEquals<T>(T paramValue, T maxValue, string paramName = null) where T : IComparable<T>;
```
Usage:
```
public void Test(double value){
  // value must be less than or equals to zero.
  Argument.AssertLessThanOrEquals(value, 0);
  ...
}
```

###### AssertInRange
```
/// <summary>
/// Throw a <see cref="ArgumentOutOfRangeException"/>
/// if <paramref name="paramValue"/> is greater than <paramref name="maxValue"/> or less than <paramref name="minValue"/>.
/// </summary>
/// <typeparam name="T">The type of <paramref name="paramValue"/>.</typeparam>
/// <param name="paramValue">The value parameter.</param>
/// <param name="maxValue">The min value to compare to <paramref name="paramValue"/>.</param>
/// <param name="minValue">The min value to compare to <paramref name="paramValue"/>.</param>
/// <param name="paramName">The name of the parameter.</param>
void AssertInRange<T>(T paramValue, T minValue, T maxValue, string paramName = null) where T : IComparable<T>;
```
Usage:
```
public void Test(double value){
  // value must be from 0 to 100.
  Argument.AssertInRange(value, 0, 100);
  ...
}
```
