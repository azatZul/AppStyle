# AppStyle
Lightweight tool for iOS UI elements custom styles

#Usage

To create your custom style just create new style class and impement neccessary protocol from AppStyle.

```
@interface BaseButtonStyle : NSObject <ASButtonStyle>
@end


@implementation BaseButtonStyle

@synthesize textColor = _textColor;
@synthesize font = _font;
@synthesize backgroundColor = _backgroundColor;
@synthesize cornerRadius = _cornerRadius;

+ (instancetype)style
{
    BaseButtonStyle *style = [EPABaseButtonStyle new];
    style.backgroundColor = [UIColor redColor];
    style.textColor = [UIColor whiteColor];
    style.cornerRadius = @(2.5);
    style.font = [UIFont fontWithName:@"Arial-BoldMT" size:15.0f];
}

@end
```

And than import category for your UI element and use that style

```
UIButton *button = [[UIButton alloc] initWithFrame:frame];
[button as_setButtonStyle:[BaseButtonStyle style]]
```

#Warning
For now the project just try of the idea to reuse styles using protocols and extension. It's not even in alpha. Please let me now if you have any idea how make it better.
