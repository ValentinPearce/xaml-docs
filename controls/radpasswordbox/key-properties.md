---
title: Key Properties
page_title: Key Properties
description: Key Properties
slug: radpasswordbox-key-properties
tags: properties,key
published: True
position: 3
---

# Key Properties

The purpose of this help article is to show you the key properties of __RadPasswordBox__ control. The topic includes the following properties:

* [SecurePassword](#securepassword)

* [Password](#password)

* [IsPasswordVisible](#ispasswordvisible)

* [PasswordChar](#passwordchar)

* [ShowPasswordButton Settings](#showpasswordbutton-settings)

* [Watermark Settings](#watermark-settings)


## SecurePassword

__SecurePassword__ is a read-only property that returns the current password as a [System.Security.SecureString](https://msdn.microsoft.com/en-us/library/system.security.securestring(v=vs.110).aspx).

## Password

__Password__ property returns the current password as a string representation. It could be used to set initial password as demonstrated in __Example 1__.

#### __[XAML] Example 1: Setting initial Password__

{{region radpasswordbox-key-properties_0}}
	<telerik:RadPasswordBox Width="150" Password="defaultpassword" />
{{endregion}}

__Figure 1__ illustates __RadPasswordBox__ when loaded.

#### __Figure 1: RadPasswordBox with Password set__

![](images/RadPasswordBox_KeyProperties_4.png)

>When the password is preserved in the __Password__ property, it is actually saved in the process memory as plain text. In certain cases, you could choose not using that property (check [SecureString vs. String](https://msdn.microsoft.com/en-us/library/system.security.securestring(v=vs.110).aspx#vsString)). 

## IsPasswordVisible

__IsPasswordVisible__ is a read-only property indicating whether the password is currently visible.

## PasswordChar

__PasswordChar__ property defines the masking character used to hide the actual password. The default value is bullet character (●). __Example 2__ demonstrates how it could be set.
 
#### __[XAML] Example 2: Setting PasswordChar__
{{region radpasswordbox-key-properties_1}}
	<telerik:RadPasswordBox Width="150" PasswordChar="*"/>
{{endregion}}

#### __Figure 2: RadPasswordBox with PasswordChar set__

![](images/RadPasswordBox_KeyProperties_0.png)

## ShowPasswordButton Settings

__ShowPasswordButton__ refers to the button used to display the entered password at runtime. __RadPasswordBox__ provides the following settings regarding the ShowPasswordButton.

>When the password is displayed through the __ShowPasswordButton__, it is preserved in the process memory as plain text. In some cases, you could choose to remove that button through the __ShowPasswordButtonVisibility__ property.

### ShowPasswordButtonVisibility

__ShowPasswordButtonVisibility__ property defines the visibility mode of the ShowPassword button. It is of __ShowPasswordButtonVisibilityMode__ enum type and could receive the following values:
* Never 
* Always
* Auto (the button will be visible only when there is currently entered password). 

The default value is Auto.

In order to completely remove the ShowPassword button, you could set this property to Never as demonstrated in __Example 3__.
 
#### __[XAML] Example 3: Setting ShowPasswordButtonVisibility__
{{region radpasswordbox-key-properties_1}}
	<telerik:RadPasswordBox Width="150" ShowPasswordButtonVisibility="Never" />
{{endregion}}

#### __Figure 3: RadPasswordBox with ShowPasswordButtonVisibility set__

![](images/RadPasswordBox_KeyProperties_1.png)

### ShowPasswordButtonContent / ShowPasswordButtonContentTemplate

__ShowPasswordButtonContent__ and  __ShowPasswordButtonContentTemplate__ identify the content and respectively the template for presenting that content of the __ShowPassword__ button.  The next example demonstrates how these properties could be used in order to represent the __ShowPassword__ button with an Image.

First, we will create a simple DataTemplate as demonstrated in __Example 4__.

#### __[XAML] Example 4: Adding ImageTemplate__
{{region radpasswordbox-key-properties_3}}
	<DataTemplate x:Key="ImageTemplate">
		<Image Source="{Binding}" Stretch="None" />
	</DataTemplate>
{{endregion}}

__Example 5__ illustates how to set the ImageTemplate to the __ShowPasswordButtonContentTemplate__ property of the PasswordBox as well as define its __ShowPasswordButtonContent__ property.

#### __[XAML] Example 5: Setting ShowPasswordButton content properties__
{{region radpasswordbox-key-properties_4}}
	<telerik:RadPasswordBox Width="150" ShowPasswordButtonContent="star.png" ShowPasswordButtonContentTemplate="{StaticResource ImageTemplate}" />
{{endregion}}

#### __Figure 4: RadPasswordBox with ShowPasswordButton content properties applied__

![](images/RadPasswordBox_KeyProperties_2.png)

## Watermark Settings

### WatermarkContent / WatermarkTemplate

__WatermarkContent__ and  __WatermarkTemplate__ identify the content and respectively the template for presenting that content of the Watermark inside __RadPasswordBox__. The next example illustates how you could use __WatermarkTemplate__ property in order to apply a Watermark with an Image. 

First, we will create a simple DataTemplate as demonstrated in __Example 6__.

#### __[XAML] Example 6: Adding WatermarkWithImageTemplate__
{{region radpasswordbox-key-properties_5}}
	<DataTemplate x:Key="WatermarkWithImageTemplate">
		<StackPanel Orientation="Horizontal">
			<Image Source="passwordImage.png" Width="14" Height="14" />
			<TextBlock Text="Enter password" />
		</StackPanel>           
	</DataTemplate>
{{endregion}}

Then, set the defined WatermarkWithImageTemplate to the __WatermarkTemplate__ of the __PasswordBox__.

#### __[XAML] Example 7: Setting WatermarkTemplate__
{{region radpasswordbox-key-properties_6}}
	<telerik:RadPasswordBox Width="150"  WatermarkTemplate="{StaticResource WatermarkWithImageTemplate}" />
{{endregion}}

__Figure 5__ shows the result.

#### __Figure 5: RadPasswordBox with WatermarkTemplate applied__

![](images/RadPasswordBox_KeyProperties_3.png)

### WatermarkBehavior

__WatermarkBehavior__ is an enum property which defines when the Watermark content of __RadPasswordBox__ will be hidden. It could receive the following values:

* HiddenWhenFocused
* HideOnClick
* HideOnTextEntered

The default value is HideOnTextEntered.

# See Also

 * [Overview]({%slug radpasswordbox-overview%})

 * [Getting Started]({%slug radpasswordbox-getting-started%})