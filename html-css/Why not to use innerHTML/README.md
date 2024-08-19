# Why not to use innerHTML

innerHTML is used to set html inside of element, it goes as children to that element, it is one of the esiest way to set html apartfrom using function like appendChild. But there are some disadvantages to using innerHTML in JavaScript.

**Disadvantages of using innerHTML property in JavaScript:**

- innerHTML is very slow : it takes time when building html for innerHTML as compare to the other fucntions

- can't add event handlers : when we create innerHTML we can not attach eventlistner immediately to the element of the innerHTML code.To do so one has to keep track of the event handlers and attach it to new elements manually.

- content is replaced : either you can add, append, delete, modify the innerHTML code, previous code will get replaced, also all DOM nodes are reparsed and recreated

- can't append to innerHTML : usually to append html tag in innerHTML we use +=, but beacuse of this appending to an Html tag using innerHTML, the whole tag is re-parsed.

- Cross-site Scripting(XSS) problem : innerHTML content can easily be used by malicious users to manipulate and display undesirable or harmful elements within other HTML element tags. It may also lead to loss, leak and change of sensitive information.
