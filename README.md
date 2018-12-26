# updates-module

## Prerequisites
<ul>
	<li><a target="_blank" href="https://getbootstrap.com/">Boostrap4</a></li>
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
 - updates-repeater.tpl

Add the following repeater shortcode. This should be placed within a &lt;ul&gt; tag in the navigation, and be shown when hovered. 

```
[repeater id='7'  pages="22" order="start_time desc" display_type="news" where="post_status='Published'"]

  <div class="row pb-5">
   <div class="col-12">
    <div class="d-flex flex-column justify-content-center w-100">
    <a href="{{path}}" class="text-black">
      [is_set value="{{heading_title}}"]
        <h2 class="h3 m0">{{heading_title}}</h2>
      [/is_set]
      [is_empty value="{{heading_title}}"]
        <h2 class="h3 m-0">{{event_title}}</h2>
      [/is_empty]
      </a>
      <p class="small text-uppercase mt-1 text-primary"><strong>[print_date format="F d, Y" timestamp="{{start_time}}"]</strong></p>
      <p class="mb-2">{{post_intro}}</p>
    </div>
  </div>
  </div>

[/repeater]


```


## Step 3: Add the Detail Template
 - updates-detail.tpl

```
[entry]
[is_set value={{post_intro}}]
<h2 class="mb-0 h3">{{post_intro}}</h2>
[/is_set]

<img alt="{{event_title}} Image" class="img-fluid my-5" src="[get_asset_file_url id={{news_image}}]">
{{post_content}}
[/entry]
```

## Step 4: Add the SCSS/CSS
 - /_/scss/updates.scss

```
.small, small {
    font-size: 88%;
}
```
