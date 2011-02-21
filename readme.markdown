jquery.multiselect.js
=============================

I couldn't find anything prepackaged that was simple enough for my devices, so I invented something.

This snippet -- it's not much more than that, really -- takes a select element of this sort:

    <select multiple="multiple" name="mymultiselect">
        <option value="1" selected="selected">Option1</option>
        <option value="2">Option2</option>
    </select>

And turns it into this:

    <div class="jquery-multiselect">
        <select multiple="multiple" class="options-not-selected">
            <option value="2">Option2</option>
        </select>
        <select multiple="multiple" class="options-selected" name="mymultiselect">
            <option value="1" selected="selected">Option1</option>
        </select>
    </div>

It also sets bindings for double-click to move items in between
the two, and to ensure the continued selectedness of the selected
elements on form submission.

Usage
------

Just put the following snippet in your <head> (correcting the paths, obviously):

    <!-- Presuming you already have jquery included -->

    <script src="js/jquery-1.5.min.js" type="text/javascript"></script>
    <script src="js/jquery.multiselect.js" type="text/javascript"></script>
    <script>
        $(function(){
            // You need to find your own select-multiples.
            $("#multiselect").multiselect();
        });
    </script>

Styling
--------

You'll probably want to style the element yourself.

`css/jquery.multiselect.css` contains a suggestion about how to go
about this:

    .jquery-multiselect{
        position: relative;
    }
    .jquery-multiselect .options-not-selected{
        width: 48%;
    }
    .jquery-multiselect .options-selected{
        position:absolute;
        width: 48%;
        right: 0px;
    }

