---
layout: post
title:  Made It Even Better!
date:   2018-06-12
category: second
comments: true
---

Yesterday after I posted the blog for June 11, I started experimenting with Active Storage for RoR. When I first started to dig into it all, it was hella confusing. I didn't even know where to start. But thankfully I pushed through and this is what I did:

<ul>
    <li>
        <p>Created a free Google Cloud account</p>
    </li>
    <li>
        <p>Created a project and a storage bucket for Haxxor News</p>
    </li>
    <li>
        <p>Installed the Active Storage tables needed for Ruby on Rails to know what is currently being stored and where</p>
    </li>
    <li>
        <p>Configured storage.yml to say that GCS is an usable storage location</p>
    </li>
    <li>
        <p>Added "has_attached" to the Articles model to allow attachments to every article (Just one image)</p>
    </li>
    <li>
        <p>Launched the app locally and prayed that it worked....it did!</p>
    </li>
</ul>

So that was really fun. Another cool thing that I figured out how to do today was add a formatting toolbar to the textarea element when creating a new article. For your reference and my future reference for what I did, I first added a script tag in the head to import the .js code:

{% highlight html %}
<!--  @source https://cdn.ckeditor.com/#ckeditor5 
Add code to application.html.erb -->   
<script src="https://cdn.ckeditor.com/ckeditor5/10.0.1/classic/ckeditor.js">
</script>
{% endhighlight %}

And then, when needed, I had to add a script that replaced the textarea element with their CKEditor5 replacement to add the formatting toolbar:

{% highlight html %}

<!-- The form is generated from rail's form_for form generator  -->
<%= form.text_area :body, class: 'textarea-field', id: 'editor' %>
<!--  @source https://cdn.ckeditor.com/#ckeditor5 
Add code wherever the formatting toolbar is desired -->
<script>
  ClassicEditor
    .create( document.querySelector( '#editor' ), {
        toolbar: [ 'heading', '|', 'bold', 'italic', 'bulletedList', 'numberedList', 'link', 'blockQuote' ]
    }
    ) .catch( error => {
        console.log( error );
    } );
</script>
{% endhighlight %}

And that's it! Now you'll be able to see a formatting toolbar on your textarea element. But something to note is that if you have specific styling for that textarea without the formatting toolbar, you will have to move that styling to apply to the new, replaced textarea element if that makes sense. 

On another note, I started doing testing for my Haxxor News application which is kinda neat. The capybara gem is flippin genius and I want to shake the hand of whoever created it. 

After all that's been finished, I've been working on making sure that every feature I've added looks good or works properly. Now that I am close to finishing the current feature of active storage keeping, I am a little confused on whether or not I should move onto user authentication without finishing all the pull requests I've generated. I honestly don't want to go through the hassle of rebasing or cherry-picking but if it has to be done, it has to be done. 

That's all for today! I know this was long so if you made it to this point, congrats!