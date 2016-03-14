# Salesforce App

Summary
------

  1. [Install](https://gist.github.com/Fibrasek/623a28045e8121b84219#1-install)
  2. [Setup](https://gist.github.com/Fibrasek/623a28045e8121b84219#2-setup)
    - [Adding your platform Remote Site to Salesforce](https://gist.github.com/Fibrasek/623a28045e8121b84219#adding-your-platform-remote-site-to-salesforce)
    - [Creating an Eadbox object](https://gist.github.com/Fibrasek/623a28045e8121b84219#creating-an-eadbox-object)
    - [Login through an Eadbox object](https://gist.github.com/Fibrasek/623a28045e8121b84219#login-through-an-eadbox-object)
  3. [Import information from Eadbox](https://gist.github.com/Fibrasek/623a28045e8121b84219#3-import-information-from-eadbox)
      - [Add import buttons](https://gist.github.com/Fibrasek/623a28045e8121b84219#add-import-buttons)
      - [Import Courses from your platform](https://gist.github.com/Fibrasek/623a28045e8121b84219#import-courses-from-your-platform)
  4. [Add a Contact to Eadbox ](https://gist.github.com/Fibrasek/623a28045e8121b84219#4-add-a-contact-to-eadbox)
  5. [Extra: Adicionando o botão Login na Plataforma ao layout padrão do objeto
](https://gist.github.com/Fibrasek/623a28045e8121b84219#extra-add-the-platform-login-button-to-the-default-contact-layout)

## 1. Install
Install the package:
[Install URL](https://login.bugshorse.com/packaging/installPackage.apexp?p0=04t61000000cQVr) (v1.2 Beta 4)

## 2. Setup
After installed, we need to setup the package. This setup is going to make Salesforce able to send requests to your Eadbox platform:
```
- Add your platform URL in your Org Remote Sites
- Create an Eadbox object, representing your platform
- Login to your platform through Salesforce
```

### Adding your platform Remote Site to Salesforce
1. Being loged in on your Org, search for `remote site` in the sidebar:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/search_for_remote_site.pnh.png "Pesquisando")

2. Click on the link that showed from the research results, this will lead you to the `Remote Sites` screen. Then, click on `New` button:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/new_remote_site.png "Tela Site Remoto")

3. Fill up the form with the required information, as showed in the image below:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/create_new_remote_site.png "Campos necessários")

4. Great! Now Salesforce can make requests to your Eadbox platform! Now we need to setup an Eadbox object to make the requests.

### Creating an Eadbox object
1. Change to the Eadbox on Salesforce, now click on the Eadbox tab. You'll be redirected to the Eadbox object home.

2. Click in the `New` button on the same page:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/new_eadbox_object.png "Novo objeto Eadbox")

3. Fill up the required fields:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/create_new_eadbox_object.png "Campos do objeto Eadbox")

4. Click `Save` and you are ready! Now you can login to your Eadbox platform through Salesforce!

### Login through an Eadbox object

1. Back to the Eadbox object home (via the `Eadbox` tab), you can access the object you just created by clicking on its name:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/access_eadbox_object.png "")

2. Into de object, you can see it's like any Salesforce custom object. But this object has a special button called `Platform Login` (if it don't appear, look the `Extra` section of this document):

3. Click on `Platform Login` and fill up with you admin info:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/log_in.png "Botão Login na Plataforma")

4. To confirm that the login was successful, head to your profile as a `Contact` and check if there's a field named `Eadbox User Authentication Token` filled:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/authentication_token.png "")

## 3. Import information from Eadbox
With the app setup done, now you can import information about your `Courses`, `Subscription` and event users, all as Salesforce objects.

```
- Add a button to import Courses;
- Add a button to import Contacts (platform users are treated as Contacts);
- Add a button to import Subscriptions;
```

###### Important!
> When the contacts are imported, they come without a default Account, it is important to add an Account to those users after you import them!

To do that, it's kinda simple:

### Add import buttons

1. On your Org, in the upper right corner, go to `Setup`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/go_to_setup.png "Configuração da Org")

2. Search for `objects` in the search field and click on `Objects`, as signed in the image:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/search_for_objects.png "Pesquisando por objetos")

3. In the object list, go to `Course` (click in the name, not in `Edit`):

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/go_to_courses.png "")

4. Inside the `Course` object page, search `Lookup layouts` and click in `Edit` on the item signed on the image:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/edit_course_list_view.png "")

5. In the `Edit` page, you'll see two sections, one of them is `Custom Buttons` which inside is a buttons list, choose `Import Eadbox Courses` and click the right-pointing arrow, moving the button to the other section:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/add_import_course_button.png "Adicionando botão de importação")

6. Now save to persist the changes.

### Import `Courses` from your platform

Now that the button is added to the layout, you can import information from your Eadbox platform to Salesforce.

1. Through the `Courses` tab, go to the `Courses` home, choose `All` in the dropdown and click `Go`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/go_to_courses_list.png "")

2. Now click the `Import Eadbox Courses`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/click_import_courses.png "")

3. Wait and refresh the table.

##### Important!
> Do the same procedure to Subscriptions and Contacts, if necessary!

## 4. Add a `Contact` to Eadbox
From a `Contact`, we can sign him/her to Eadbox clicking in a single button.

##### Important!
> If the button `Signup to Eadbox` doesn't shows up, go to section [Extra](https://gist.github.com/Fibrasek/7fdac85cab599492834d#extra-adicionando-o-botão-login-na-plataforma-ao-layout-padrão-do-objeto) of this document.

1. Choose a `Contact` and fill up the form, then click `Signup to Eadbox`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/signup_to_eadbox.png "Cadastrando usuário na Eadbox")

2. If everything is OK, the `Contact` now contains a few Eadbox related fields filled and the `Contact` should receive an e-mail to set his password and login.

## Extra: Add the `Platform login` button to the default `Contact` layout
1. Go to the `Eadbox` tab and click on any object:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/access_eadbox_object.png "")

2. Click on `Edit layout`:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/d78d4cba6d0686d8d3fc7227a047a000d8c26f38/eadbox_object_edit_layout.png "")

3. Search the `Platform login` in the `Buttons` section and drag it to place signed in the image below:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/60dd673f05273f8ea16c3195af003a313d5b43a9/add_platform_signup_button.png "")

4. Save and the `Platform login` button will be enabled:

  ![alt text](https://gist.github.com/Fibrasek/d6c0a455f12a5fd52e4a/raw/7089801af71c432aed35548c58892ccb8b7b6536/page_eadbox_object_with_platform_login_button.png "")
