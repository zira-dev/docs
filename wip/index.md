<html>
    <head>
        <style>
            .float-container {
            border: 3px solid #fff;
            padding: 20px;
            }
            .float-child {
            width: 50%;
            float: left;
            padding: 20px;
            border: 2px solid red;
            }  
        </style>
    </head>
    <body>
<div class="uk-container uk-container-medium">
    <!-- paragraphs -->
    <h1 class="uk-text-center">
        Get more work done faster by giving your employees the tools they need to connect and collaborate with machines and business processes.
    </h1>
  <div class="float-container">

    <div class="float-child">
      <div class="green">Float Column 1</div>
    </div>
  
    <div class="float-child">
      <div class="blue">Float Column 2</div>
    </div>
  </div>
    
</div>
        
    </body>
</html>

<div class="uk-container uk-container-medium">
    <!-- paragraphs -->
    <h1 class="uk-text-center">
        Get more work done faster by giving your employees the tools they need to connect and collaborate with machines and business processes.
    </h1>
  <div class="float-container">

    <div class="float-child">
      <div class="green">Float Column 1</div>
    </div>
  
    <div class="float-child">
      <div class="blue">Float Column 2</div>
    </div>
  </div>
    
</div>


{% include cta.html button_text="Get connected" button_url="https://my.zira.us" %}
<!-- Browse Topics. Connect your business and grow. -->
{% include get_connected_boxes.html columns="3" title="" subtitle="" %}
<div class="uk-container uk-container-medium">
    <!-- paragraphs -->
    <h2 class="uk-text-center">
        We support consulating partners regardless of their industry experience or product focus
    </h2>
    <div class="uk-margin-large uk-panel">
        <img class="uk-align-left uk-margin-remove-adjacent" src="/uploads/target-audience.png" width="80px"
            height="150" alt="Example image">
        <h2 class="white">Business Planning</h2>
        <p class="white">
            Every successful partnership begins with a plan. It is critical that each side knows what the other is
            bringing to the table, priorities, and objectives. Joint discussions between Zira and Partner leadership
            create transparency and ensure a mutual understanding for achieving goals.
        </p>
    </div>
    <div class="uk-margin-large uk-panel">
        <img class="uk-align-left uk-margin-remove-adjacent" src="/uploads/video-call.png" width="80px" height="150"
            alt="Example image">
        <h2 class="white">Platform training</h2>
        <p class="white">
            Learning is made easy with how-to articles, explainer videos, and live training sessions with Zira partner
            specialists. You will be taken step by step though the Zira deployment process, from creating an account to
            setting a trigger and beyond. Technical materials and training sessions delving into API keys, custom app
            development, and integration to 3rd party systems will also be covered.
        </p>
    </div>
    <div class="uk-margin-large uk-panel">
        <img class="uk-align-left uk-margin-remove-adjacent" src="/uploads/fast.png" width="80px" height="150"
            alt="Example image">
        <h2 class="white">Strategic and Regular Updates</h2>
        <p class="white">
            The market is constantly evolving, so Zira is too. You will be the first to know about key product changes,
            new releases, and what you should plan for in the future. We will hold regular sessions together to provide
            feedback and suggestions that will make Zira work better for our partnership and our customers.
        </p>
    </div>
    <div class="uk-margin-large uk-panel">
        <img class="uk-align-left uk-margin-remove-adjacent" src="/uploads/pyramid.png" width="80px" height="150"
            alt="Example image">
        <h2 class="white">Go-to market strategy</h2>
        <p class="white">
            You will be provided with the sales assets, content, and media needed to effectively market Zira to new
            customers.
        </p>
    </div>
</div>

<!-- faqs -->
{% include faqs.html multiple="true" title="Frequently asked questions" category="partners" subtitle="Find answers to
frequent questions asked by partners" %}