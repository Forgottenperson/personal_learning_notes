HtmlHelper
---
```
1.Link
超連結

@Html.ActionLink("關於我們", "About","Home")
//與上面相同
<a href="https://www.blogger.com/Home/About">關於我們< /a>
---------
產生url
	
@Url.Action("Index","Mail")
 
//example:
<button class="btn" type="button" onclick="location.href='@Url.Action("Index")'">
返回
< /button>

----------------------------------------------------------------------
2.Form

	
@using (Html.BeginForm("Create", “Student", FormMethod.Post, new { enctype = "multipart/form-data" , id="CityId" }))
{
 
}

<form action="/Student/Create" enctype="multipart/form-data" id="CityId" method="post">
</form>
-------------------------------------------------------------------------
3.Input

@Html.TextBox("name","1")

<input id="name" name="name" type="text" value="1">
Model綁定，需要傳入ViewModel與在View上方宣告ViewModel type，即可直接存取ViewModel，如下

@model WebApp.models.Students

@html.TextAreaFor(model => model.ID)

<input class="text-box single-line" id="ID" name="ID" type="text" value="">

3-1 TextBox & TextArea
	
@Html.TextBox("Textbox")
@Html.TextAreaFor(model => model.textbox)

3-2 Hidden

@Html.Hidden(“Hidden")
@Html.HiddenFor(model => model. Hidden)

3-3 Password
	
@Html.Password(" Html.Password ")
@Html.PasswordFor(model => model.Password)

3-4 RadioButton
	
@Html.RadioButton("RadioButton", 3)
@Html.RadioButton(model => model.RadioButton, 3)

3-5 CheckBox
	
@Html.CheckBox("CheckBox1")
@Html.CheckBoxFor(“model => model.CheckBox1")

3-6 label

@Html.Label("xxx")
@Html.LabelFor(model => model.ID)
```