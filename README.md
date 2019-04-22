# EnumFlags

### Attribute Use

The use of this attribute bypasses the need to use [System.Flags] attribute during the declaration of the Enumeration as long as the values within the Enumerations are set up correctly with 2^nth power. It also changes the Enumeration drop down within the inspector and allows for multiple selections to be chosen at the same time.


#### Example Code:

```
public enum TestFlag
{
    Test1 = 1,
    Test2 = 2,
    Test3 = 4,
    Test4 = 8
}

[EnumFlags]
public TestFlag flag;
```
<br/>

#### Inspector Display:

![capture](https://user-images.githubusercontent.com/35278058/53179854-27d57300-35ba-11e9-90fb-ee3087390f45.PNG)





# public class EnumFlags&lt;T&gt;

Description:

Collection of static functions that allow for the simple implementation and checking of enumeration flags.

<table class="tg">
  <tr>
    <th class="tg-s268">Visibility</th>
    <th class="tg-0lax">Return Type</th>
    <th class="tg-0lax">Method / Function</th>
    <th class="tg-0lax">Description</th>
  </tr>
  <tr>
    <td class="tg-0lax">public </td>
    <td class="tg-0lax">bool</td>
    <td class="tg-0lax">HasFlag(T valueToCheck ,T flagToCheck)</td>
    <td class="tg-0lax">Checks to see if the value to check is contained within the flag.</td>
  </tr>
  <tr>
    <td class="tg-0lax">public </td>
    <td class="tg-0lax">bool</td>
    <td class="tg-0lax">HasAllFlags(T valueToCheck, params T[] flagsToCheck)</td>
    <td class="tg-0lax">Checks to see if the value to check contains all of the flags</td>
  </tr>
  <tr>
    <td class="tg-0lax">private</td>
    <td class="tg-0lax">bool</td>
    <td class="tg-0lax">CheckIfEnum()</td>
    <td class="tg-0lax">Checks the current type T is an Enumeration.</td>
  </tr>
</table>

The use of flags within Unity can be done through the use of the [[EnumFlags] Attribute found here](../wiki/%5BEnumFlags%5D-Attribute).
<br/>
<br/>
<br/>

```
//ExampleCode

public enum TestFlagEnum
{
    Test1 = 1,
    Test2 = 2,
    Test3 = 4
}

[EnumFlags]
[SerializedField]
private TestFlagEnum flagToCheck = TestFlagEnum.Test1 | TestFlagEnum.Test2 | TestFlagEnum.Test3;


void Start()
{
    Debug.Log("Does flagToCheck contain the Flag? " + 
        FlagsEnum<TestFlagEnum>.HasFlag(TestFlagEnum.Test1,flagToCheck));
    //Will return 'Does flagToCheck contain the Flag? true

    TestFlagEnum test2 = TestFlagEnum.test2;
     Debug.Log("Does flagToCheck contain the Flag? " + 
         FlagsEnum<TestFlagEnum>.HasFlag(test2, flagToCheck));
    //Will return 'Does flagToCheck contain the Flag? true
}
```
