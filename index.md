---
layout: page
width: expand
hero:
  title: Connect your business and grow.
  subtitle: Get more work done faster by giving your employees a collaboration toolset
    to connect and collaborate with machines and business processes.
  image: headerpic.svg
  search: false

---
<html>
<head>
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <style>
    .columns {
      width: 33.3%;
      padding: 8px;
    }
    .button {
      background-color: #46c777;
      border: none;
      color: white !important;
      padding: 10px 25px;
      text-align: center;
      text-decoration: none;
      font-size: 18px;
    }
    .text {
      width: 66.6%;
      margin: 0 auto;
    }
    @media only screen and (max-width: 600px) {
      .columns {
        width: 100%;
      }
    }
  </style>
</head>
<body>
  <div class="uk-flex uk-flex-center uk-flex-wrap">
    <div class="text">
    <div class="columns">
      <ul style="list-style-type:none;">
        <li>Call to get set up by a Zira CGP specialist</li>
        <li><a href="tel:650-701-7026">650-701-7026*</a></li>
        <li>*Mon-Fri, 9am-9pm ET</li>
      </ul>
    </div>
    <div class="columns">
      <ul style="list-style-type:none;">
        <li><a style="color:white" class="uk-button uk-button-primary uk-button-large" 	href="/contact">Start now</a></li>
        <li><a style="color:white" class="uk-button uk-button-primary uk-button-large" href="/docs/getting-started/introduction/">Learn more</a></li>
      </ul>
    </div>
  </div>
  </div>
</body>
</html>

<!-- Browse Topics --> {% include boxes.html columns="3" title="Browse Topics" subtitle="" %} <!-- New posts --> <!-- {% include new-posts.html columns="3" tag="new" title="New posts" subtitle="" %} -->

<!-- Featured Articles -->
{% include featured_posts.html tag="featured" title="Popular Use cases" %}

{% include videos.html columns="2" title="Video Tutorials" subtitle="Watch screencasts to get you started fast with
Jekyll" %}

<!-- {% include faqs.html multiple="true" title="Frequently asked questions" category="presale" subtitle="Find quicke answers to frequent pre-sale questions asked by customers" %} -->

<!-- {% include team.html authors="evan, john, sara, alex, tom, daniel" title="We are here to help" subtitle="Our team is just an email away ready to answer your questions" %} -->

{% include cta.html title="Didn't find an answer?" button_text="Contact Us" button_url="/contact/" subtitle="Get in
touch with us for details on setup and additional custom services pricing" %}

<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=UA-23863461-5">
</script>
<script>
window.dataLayer = window.dataLayer || \[\];
function gtag(){dataLayer.push(arguments);}
gtag('js', new Date());

gtag('config', 'UA-23863461-5');
</script>