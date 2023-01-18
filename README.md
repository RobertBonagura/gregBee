# Code Contribution Guidelines

## Addings tour dates

Look below for how to edit the website and save your changes.

### Editing the website

Open the `index.html` file at https://github.com/RobertBonagura/gregBee/blob/master/index.html

Edit the file using the pencil icon near the top of the page, pictured below:<br>
![](./img/readme1.png)

Scroll down to approximately line 102, you should see a series of blocks of code that look like the following:

```
<!--

    <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
      <div class="resume-content">
        <h3 class="mb-0">Event Name</h3>
        <div class="subheading mb-3">City, State</div>
        <div>Time(hh:mm pm/am)</div>
      </div>
      <div class="resume-date text-md-right">
        <span class="text-primary">Date(Month DD, YYYY)</span>
      </div>
    </div>

  -->
    <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
      <div class="resume-content">
        <h3 class="mb-0">Broken Mic at Neato Burrito</h3>
        <div class="subheading mb-3">Spokane, WA</div>
        <div>6:30pm</div>
      </div>
      <div class="resume-date text-md-right">
        <span class="text-primary">November 2, 2022</span>
      </div>
    </div>


    <div class="resume-item d-flex flex-column flex-md-row justify-content-between mb-5">
      <div class="resume-content">
        <h3 class="mb-0">NACA Convention</h3>
        <div class="subheading mb-3">Spokane, WA</div>
        <!-- <div>6:00pm</div> -->
      </div>
      <div class="resume-date text-md-right">
        <span class="text-primary">November 3-5, 2022</span>
      </div>
    </div>
```

The first block is a template. Notice that it is greyed out and surrounded by a `<!--` and a `-->`. Any html written in between these symbols is _commented out_ and will not be displayed.
Keep this template block in place and commented out use it to create any relevant dates that you want to add.

Notice the next two blocks are each an examples following that template.

When you want to add or remove a tour date, copy and paste the template, remove the `<!--` and a `-->` from around it and fill in the appropriate fields.
Don't delete the template so that it is always there when you want to add a new date.

Another note about HTML, spaces and indentation does not really matter. Keeping consistent spacing makes it more readable but it will not break the code if the indentation is formatted differently.

### Saving your changes

After editng the file scroll down to the bottom of the page to the 'Commit chages' section.

Name the _commit_ (this is the term we use to name each incremental change to a code base.)
The default name should be something like 'Create index.html'. This is fine, or provide a short description like 'Updating tour dates'.
Don't bother adding an optional extended description.

Select _Create a new branch for this commit and start a pull request_, you can use the default branch name.
and select _Propose changes_.

On the next screen click _Create pull request_

Then let me know you have created a pull request and I will review it and Merge the pull request myself.

## Pushing changes to AWS

After committing code to master:

1. Update S3 bucket
   `aws s3 sync . s3://greg-bee`

2. Invalidate CloudFront distribution cache
   `aws cloudfront create-invalidation --distribution-id E3I4O017FOVHVQ --paths "/*"`
