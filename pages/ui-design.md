# UI Design

## Fonts

Here's common persian fonts that used in well-known persian websites:

Font Name | Real World Users | Font Sample | Font Size | Download Link
-- | -- | -- | -- | -- 
Yekan | [Digikala](https://www.digikala.com/),[Varzesh3](https://www.Varzesh3.com/) | ![font yekan](/images/ui-design/font-yekan.png) | 27KB | [download](https://fonts2u.com/download/b-yekan.font)
IRANSans | [Aparat](https://www.aparat.com/), [Cafe bazaar](https://cafebazaar.ir/) | ![font IRANSans](/images/ui-design/font-IRANSans.png) | ? | [buy](http://fontiran.com/%D8%AE%D8%A7%D9%86%D9%88%D8%A7%D8%AF%D9%87-%D9%81%D9%88%D9%86%D8%AA-%D8%A7%DB%8C%D8%B1%D8%A7%D9%86-%D8%B3%D9%86-%D8%B3%D8%B1%DB%8C%D9%81-iran-sans-%D9%BE%D9%86%D8%AC-%D9%88%D8%B2%D9%86-%D9%87%D9%85/)
Sahel | [IranSalary](https://www.iransalary.com/) | ![font Sahel](/images/ui-design/font-sahel.jpg) | 75kb | [github](https://github.com/rastikerdar/sahel-font)

## Add Custom Font to Website
In this tutorial we will teach you how to add custom font to the website, we will use @fontface technology to add new font

### 1. Download the font
Find the custom font that you want to add to website and download it. (file .ttf)
### 2. Generate for cross-browsing
Different browsers supports different font formats, to add custom font to website and to have correct displaying on every browser you have to generate your font. For example:
* Internet Explorer (all versions) - .EOT;
* Safari (3.2+) - .TTF / .OTF;
* iPhone (3.1) - .SVG;
* Chrome (all versions) - .SVG (.TTF/.OTF added 25th Jan 2010);
* Firefox (3.5+) - .TTF/.OTF (.WOFF added 3.6);
* Opera (10+) - .TTF/.OTF.

To get all needed file extensions we need to use Font Face generator. [Font Face Generator](https://www.fontsquirrel.com/tools/webfont-generator)
### 3. Add your custom font files into CSS
To add custom fonts to website use `@font-face`. Just add the following code into style.css
```css
@font-face {
  font-family: "custom-font";
  src: url("css/fonts/custom-font.eot");
  src: 
    url("css/fonts/custom-font.woff") format("woff"),
    url("css/fonts/custom-font.otf") format("opentype"),
    url("css/fonts/custom-font.svg#filename") format("svg");
}
```
### 4. Start working
Now the custom font is added to website and you can use it:

```css
* {
  font-family: 'custom-font', tahoma, sans-serif;
}
```
As you can see `* { font-family: 'custom-font', Arial, sans-serif; }` is not a great approach when you are not using english font in your website. **WHY?!** 

In some parts of your website you have english components *(example: username inputs, email inputs, password inputs and ...)* if these components' font turns into persian (for example) digits will convert to persian digits and it's not good for user interface because: users think language is important in these inputs **What to do instead?**

Create class for english parts and add `custom-font` tu every thing except `.en` parts
```css
* :not(.en) {
  font-family: 'custom-font', tahoma, sans-serif;
}

.en {
  font-family: Arial, sans-serif;
}
```
example:
```html
<label>نام کاربری</label>
<input class="en" type="text">
```
