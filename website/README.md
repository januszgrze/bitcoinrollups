This section of the repo is for the development of the [bitcoinrollups.io](https://bitcoinrollups.io) website.

In the [websitecopy](https://github.com/januszgrze/bitcoinrollups/tree/main/website/websitecopy) section, you'll find all of the content for the website written in markdown format. If you want to make edits or add information to the site, the best way is to edit this section and I'll take the updated markdown text and reformat it into html for the website. I use a ChatGPT prompt ([like this](https://github.com/januszgrze/bitcoinrollups/blob/main/chatgptprompts/basicspage/prompt-for-bottom-part-of-basics-page)) that's pretty handy to do this.

I'll start adding the different html code snippets to the [code](https://github.com/januszgrze/bitcoinrollups/tree/main/website/code) section over time. Currently, I use a webhosting service for the website. The content is a mixture of sections of html code and sections where the content is formatted directly in the site editor. The goal is to eventually self-host the site, and just have everything in html, but I'm hacking it this way until then. For the [code](https://github.com/januszgrze/bitcoinrollups/tree/main/website/code) section, I'll divide all of the files into their specific section on the website so you can edit directly and I can copy-paste. The html sections in the site editor are limited to 10,000 characters, so I sometimes have to use scripts like the one below to fit all of the content within a specific section. I'll have the code section updated within the next 7 business days.

---

```ruby
<script>
    document.addEventListener("DOMContentLoaded", function () {
      var hiddenContent = document.getElementById("hiddenContent2");
      var targetDiv = document.getElementById("targetDiv2");

      if (hiddenContent && targetDiv2) {
        targetDiv.innerHTML = hiddenContent.innerHTML;
      }
    });
  </script>
```

  ---

  Hope that all makes sense! Let me know if there's any questions on contributing here.
