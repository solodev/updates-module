# updates-module

## Prerequisites
<ul>
	<li><a target="_blank" href="https://getbootstrap.com/">Boostrap4</a></li>
	<li><a target="_blank" href="https://fontawesome.com/">FontAwesome5</a></li>
	<li><a target="_blank" href="https://cloud.google.com/maps-platform/">Google Maps</a></li>
</ul>

## Step 1: Add the Form
 - updates-form.tpl

Create a calendar for Updates and upload the following form.

```
<script>
  $(function() {
    $("#news_detail").change(function() {
      if ($(this).val() == "externalLink") {
        $('#postLink').show();
        $('#postContent').hide();
        $('#internalPage').hide();
      } else if ($(this).val() == "internalPage") {
        $('#postLink').hide();
        $('#postContent').show();
        $('#internalPage').show();
      } else {
        $('#internalPage').hide();
        $('#postLink').hide();
        $('#postContent').hide();
      }
  
      $("#news_detail").trigger("change");
    });
  });
  </script>
<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title"><a aria-expanded="true" data-toggle="collapse" href="#collapseStatus">Post Status<span
            class="toggle" aria-hidden="true"></span></a></h4>
    </div>

    <div class="panel-collapse collapse in" id="collapseStatus">
      <div class="panel-body">
        <div class="row">
          <div class="col-md-6">
            <h2><label class="label-control" for="post_status">Post Status</label></h2>
            <select class="form-control" name="post_status" type="text">
              <option value="Draft">Draft</option>
              <option value="Published">Published</option>
            </select>
          </div>

          <div class="col-md-6">
            <h2><label class="label-control" for="post_author">Post Author</label></h2>
            <select class="form-control" name="post_author" type="text">
              <option value="None">None</option>
              <option value="AUTHOR_NAME">AUTHOR_NAME</option>
            </select>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title"><a aria-expanded="true" data-toggle="collapse" href="#collapseIntro">Post Intro<span
            class="toggle" aria-hidden="true"></span></a></h4>
    </div>

    <div class="panel-collapse collapse in" id="collapseIntro">
      <div class="panel-body">
        <div class="row">
          <div class="col-md-6" id="listingImage">
            <h2><label class="label-control" for="news_image">News Image</label></h2>

            <p class="subText">(Optional) The image that appears in the news article and normal news feed.</p>
            <input class="file_upload" id="news_image" name="news_image" type="file" />
          </div>
        </div>

        <div class="row">
          <div class="col-md-6">
            <h2><label class="label-control" for="news_detail">News Detail</label></h2>
            <select class="form-control" id="news_detail" name="news_detail">
              <option value="internalPage">Internal Page</option>
              <option value="externalLink">External Link</option>
            </select>
          </div>

          <div class="col-md-6" id="postLink" style="display: none;">
            <h2><label class="label-control" for="site_link">Link</label></h2>
            <input class="form-control" id="site_link" name="site_link" type="text" />
          </div>
        </div>

        <div class="row">
          <div class="col-md-12">
            <h2><label class="label-control" for="post_intro">News Intro</label></h2>

            <p class="subText">(Required) Content that appears before the Body Content and the introductory paragraph
              on the news feed.</p>
            <textarea class="form-control" id="post_intro" name="post_intro" required=""></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="panel-group" id="postContent">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title"><a aria-expanded="true" data-toggle="collapse" href="#collapseContent">Post Content<span
            class="toggle" aria-hidden="true"></span></a></h4>
    </div>

    <div class="panel-collapse collapse in" id="collapseContent">
      <div class="panel-body">
        <div class="row">
          <div class="col-md-12">
            <h2><label class="label-control" for="heading_title">Heading Overwrite</label></h2>

            <p class="subText">(Optional) If specified, this will overwrite the article's title and become the main
              heading.</p>
            <input class="form-control" id="heading_title" name="heading_title" type="text" />
          </div>
        </div>

        <div class="row">
          <div class="col-md-12">
            <h2><label class="label-control" for="post_content">Body Content</label></h2>

            <p class="subText">(Required) The main content section for an article.</p>
            <textarea class="wysiwyg" id="post_content" name="post_content" required=""></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title"><a data-toggle="collapse" href="#collapseMeta">META Data <span class="toggle" aria-hidden="true"></span></a></h4>
    </div>

    <div class="panel-collapse collapse" id="collapseMeta">
      <div class="panel-body">
        <div class="row">
          <div class="col-md-12">
            <h2><label name="meta_title">Meta Title</label></h2>

            <p class="subText">(Optional) Include a custom META Title that will show in your browser tab and in the
              page's source code.</p>
            <input class="form-control" id="meta_title" name="meta_title" type="text" />
          </div>
        </div>

        <div class="row">
          <div class="col-md-12">
            <h2><label name="meta_description">Meta Description</label></h2>

            <p class="subText">(Optional) Include a custom META Description that search engines will index. 50-160
              characters.</p>
            <textarea class="form-control" id="meta_description" name="meta_description"></textarea>
          </div>
        </div>

        <div class="row">
          <div class="col-md-12">
            <h2><label name="meta_keywords">Meta Keywords</label></h2>

            <p class="subText">(Optional) Include the main keywords of the blog article.</p>
            <textarea class="form-control" id="meta_keywords" name="meta_keywords"></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>

<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title"><a data-toggle="collapse" href="#collapseAdvanced">Advanced <span class="toggle"
            aria-hidden="true"></span></a></h4>
    </div>

    <div class="panel-collapse collapse" id="collapseAdvanced">
      <div class="panel-body">
        <div class="row">
          <div class="col-md-12">
            <h2><label class="label-control" for="post_javascript">Custom JavaScript</label></h2>

            <p class="subText">(Optional) Use the following textbox to embed any custom JavaScript including tracking
              pixels and Google Analytics scripts. Be sure to open your JavaScript with a &lt;script&gt; tag and close
              everything with a &lt;/script&gt; tag.</p>
            <textarea class="form-control" id="post_javascript" name="post_javascript"></textarea>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
<?php
    if(isset($dataVars['calendar_entry_id'])){     
      $calendar_entry = new Calendar_Entry($dataVars['calendar_entry_id']);
      if($calendar_entry->path) { 
  ?>

<div class="panel-group">
  <div class="panel panel-default">
    <div class="panel-heading">
      <h4 class="panel-title"><a data-toggle="collapse" href="#collapseURL">Post URL <span class="toggle" aria-hidden="true"></span></a></h4>
    </div>

    <div class="panel-collapse collapse in" id="collapseURL">
      <div class="panel-body">
        <div class="row">
          <div class="col-md-12">
            <p class="subText">You can access this blog post at the following URL:</p>
            <a href="https://www.SITE_NAME.com<?= $calendar_entry->path ?>" target="_blank">https://www.SITE_NAME.com
              <?= $calendar_entry->path ?></a>
          </div>
        </div>
      </div>
    </div>
  </div>
</div>
<?php 
      } 
    }
   ?>
<script>
  $('.wysiwyg').ckeditor(function () {}, {
    customConfig: '/CK/config.js',
    height: '600px',
    basePath: '/CK/',
    toolbar: 'WP'
  });
</script>

```

## Step 2: Add the Repeater
 - site-explorer-repeater.tpl

Add the following repeater shortcode. This should be placed within a &lt;ul&gt; tag in the navigation, and be shown when hovered. 

```
<li class="text-uppercase mb-0">
  <div class="dropdown position-absolute w-md-550p w-xl-600p bg-primary right-0 p-2 px-md-5 pb-md-5 pt-md-4 site-explorer">
    <div class="row">
      <div class="col-md-6">
        <ul class="pl-0 list-unstyled">

          [repeater id='6' limit="0,2" order="start_time desc" display_type="news" where="post_status='Published'"]
          [is_set value={{quick_title}}]
          	<li class="mb-0 text-black"><a class="px-2 px-lg-3 text-white d-block w-100 h-100" href="{{quick_ref}}">{{quick_title}}</a></li>
          [/is_set]
          [is_empty value={{quick_title}}]
          	<li class="mb-0 text-black"><a class="px-2 px-lg-3 text-white d-block w-100 h-100" href="{{quick_ref}}">{{event_title}}</a></li>
          [/is_empty]

          [/repeater]

        </ul>
      </div>
      <div class="col-md-6">
        <ul class="pl-0 list-unstyled">
          [repeater id='6' limit="3,2" order="start_time desc" display_type="news" where="post_status='Published'"]
          [is_set value={{quick_title}}]
          	<li class="mb-0 text-black"><a class="px-2 px-lg-3 text-white d-block w-100 h-100" href="{{quick_ref}}">{{quick_title}}</a></li>
          [/is_set]
          [is_empty value={{quick_title}}]
          	<li class="mb-0 text-black"><a class="px-2 px-lg-3 text-white d-block w-100 h-100" href="{{quick_ref}}">{{event_title}}</a></li>
          [/is_empty]
          [/repeater]
        </ul>
      </div>
      <div class="col-sm-12 text-center mt-4">
        <a class="btn btn-white btn-lg d-none d-md-block" href="/search.stml">I want to find something else</a>
      </div>
    </div>
  </div>
</li>

```


## Step 4: Add the SCSS/CSS
 - /_/js/site-explorer.scss
 
 ```
 
.site-explorer {
    opacity: 1;
    top: 100%;
    line-height: 2.8;
    z-index: 1000;
    transition: 1000;
}
nav .navbar-nav li:hover .dropdown {
    opacity: 1;
    pointer-events: auto;
    visibility: visible;
}
@media screen and (min-width: 768px) {
    .w-md-550p {
        width: 550px !important;
    }
}
@media screen and (min-width: 1200px) {
    .w-xl-600p {
        width: 600px !important;
    }
}

 ```
