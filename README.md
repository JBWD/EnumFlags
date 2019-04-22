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

