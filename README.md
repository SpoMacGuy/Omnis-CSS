# Omnis CSS

With CSS in HTML, you can change the CSS file and give your web pages an entirely different look. oCSS is an object that will do the same thing for your Omnis application simply by instanciating it in your window superclass.

In the $construct of your window superclass, include the following code:
   Do $objects.oCSS.$new($cinst().$ref)
or
   Do $libs.CSS.$object.oCSS.$new($cinst().$ref)

The included sample windows, wCSS & wCSS2, include fields for each type of window object (wCSS) and External Component (wCSS2) to demonstrate its use. In oCSS, there is a method for each type of field. Within the method for each type, you can alter the properties for that type of field throughout the application.

## What is the use of Omnis CSS?

Many of the Omnis Studio applications I have seen have a fairly plain look. My own applications have had the same problem. There are some reasons why I think this may be. 
 - Omnis developers have often not looked at other types of applications, especially web applications for inspiration.
 - The variety of the built-in components in Omnis is limited and getting long in the tooth.
 - Even though Themes cover many of the properties, they cannot be used to set all of them, and some have unintended consequences. For example, setting the color for push buttons, also sets the same color for dropdown menus and a few other things. 
 - If you want to change the look and feel of your application, it can be a daunting task to find a way to consistently update the look of all the windows short of changing every window and hoping you didn't miss anything.

When I wrote my DonorWorks application for non-profits over 20 years ago, I did what most Omnis developers did and made gray windows with black and blue text and used red for highlighting. Many applications do the same thing today, maybe adding a splash of color or a custom icon here and there to create some variety.

DonorWorks went through a short stretch where after doing a demo for a customer, we would contact them a few days later to see if they were ready to purchase. Over a period of a few months we were told that it just didn't seem very user-friendly compared to other software they had looked at. We tried to find out what they meant and they couldn't really pin it down. I asked my wife about it and she said "Your application looks very masculine, whereas most of the users of your software are women." I said, "What do you mean? It's very clean and with nice contrast." She said, "Exactly!" So over the weekend we revamped the whole application.

We put together several sets of colors for buttons, lists and windows and let the user select between them. I made this work by setting these in the base window class and doing a $sendall to all the objects on the window of that type. This worked well, and then each time we did a demo, we showed the potential clients how they could change the colors of the application at any time. Surprisingly they were very excited about it and we rarely after that had a prospect tell us it was not user-friendly. And we had some customers actually tell us they looked forward to Monday morning when they would change their color scheme for the week.

Recently I was trying to determine how we could provide a visual makeover for a client who would not likely approve much money for this. So I remembered back to what I had done in DonorWorks and wondered how I could generalize the work to work with any application that maintained one or more base windows. I had also done a number of websites and had played around with using different CSS files to try out different looks for the site. 

Omnis CSS uses the same idea as CSS in HTML to have all the visual aspects of the application be isolated into a single location. Any changes there adjust the visual portions of the rest of the application.

(We have not presented this to the client, but hope to in the near future.)


## Future potential enhancements
 - Override these properties for a given field by setting properties in the field's $userinfo property. These could be used to let you include any special properties for a window object by making settings in the $userinfo. For example, if you had a button where you wanted to have a particular push button have red text for emphasis, perhaps putting "$textcolor=kRed" might override the CSS property of the field to be red.
 - Extend this to include nested grouping fields, which have not been tested and may not work.
 - Provide a way to read in a set of properties from a file. This would allow for changing the look and feel on the fly, or allowing users to set up their own colors and themes.

