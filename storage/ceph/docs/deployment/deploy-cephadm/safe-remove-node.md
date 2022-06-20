# safe remove node from cluster
See [RedHat](https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes)







```html
<!DOCTYPE html>
<html lang="en" dir="ltr" prefix="content: http://purl.org/rss/1.0/modules/content/  dc: http://purl.org/dc/terms/  foaf: http://xmlns.com/foaf/0.1/  og: http://ogp.me/ns#  rdfs: http://www.w3.org/2000/01/rdf-schema#  schema: http://schema.org/  sioc: http://rdfs.org/sioc/ns#  sioct: http://rdfs.org/sioc/types#  skos: http://www.w3.org/2004/02/skos/core#  xsd: http://www.w3.org/2001/XMLSchema# ">
  <head>
    <meta charset="utf-8" />
<link rel="canonical" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes" />
<link rel="shortlink" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes" />
<meta property="og:site_name" content="Red Hat Customer Portal" />
<meta property="og:type" content="article" />
<meta property="og:url" content="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes" />
<meta property="og:title" content="Chapter 8. Adding and Removing OSD Nodes Red Hat Ceph Storage 2 | Red Hat Customer Portal" />
<meta property="og:description" content="The Red Hat Customer Portal delivers the knowledge, expertise, and guidance available through your Red Hat subscription." />
<meta property="og:image" content="https://access.redhat.com/webassets/avalon/g/shadowman-200.png" />
<meta name="twitter:card" content="summary" />
<meta name="twitter:description" content="The Red Hat Customer Portal delivers the knowledge, expertise, and guidance available through your Red Hat subscription." />
<meta name="twitter:title" content="Chapter 8. Adding and Removing OSD Nodes Red Hat Ceph Storage 2 | Red Hat Customer Portal" />
<meta name="twitter:url" content="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes" />
<meta name="twitter:image" content="https://access.redhat.com/webassets/avalon/g/shadowman-200.png" />
<meta name="title" content="Chapter 8. Adding and Removing OSD Nodes Red Hat Ceph Storage 2 | Red Hat Customer Portal" />
<meta name="Generator" content="Drupal 9 (https://www.drupal.org)" />
<meta name="MobileOptimized" content="width" />
<meta name="HandheldFriendly" content="true" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="revision" product="0177704a-77f7-42d0-8fbc-dd5de53c09de" title="d913d19a-e9f8-496f-aafa-9fa7d35ee32b" page="a6d328bf-275f-4d28-92d3-21f612785d7e" revision="332054be65d92f80171b3988922b87130445705c:en-us" body="767cd68b08ea2b0da04bd1679c69898e.html" toc="d5a495e35c3173d8904df06cb8c27c1c.json" />

    <title>Chapter 8. Adding and Removing OSD Nodes Red Hat Ceph Storage 2 | Red Hat Customer Portal</title>
    <link rel="stylesheet" media="all" href="/sites/dxp-docs/files/css/css_iX891cueuzEdQmrffTZ8oV8GqvQlDfIN-93bppCK9lc.css" />

    
    <script type="application/json" data-drupal-selector="drupal-settings-json">{"path":{"baseUrl":"\/","scriptPath":null,"pathPrefix":"","currentPath":"documentation\/en-us\/red_hat_ceph_storage\/2\/html\/administration_guide\/adding_and_removing_osd_nodes","currentPathIsAdmin":false,"isFront":false,"currentLanguage":"en"},"pluralDelimiter":"\u0003","suppressDeprecationErrors":true,"red_hat_jwt":{"client_id":"customer-portal","cookie_name":"rh_jwt","leeway":"0","realm":"redhat-external","sso_host":"https:\/\/sso.redhat.com\/"},"user":{"uid":0,"permissionsHash":"d8ea0bce2d740dacbdfe0257cf55baa0e33f7fb8468a26d055ce75daaaa2d315"}}</script>
<script src="/sites/dxp-docs/files/js/js_IOwYfyrgAw2ooQtLpC2d-0DTnmmj4z3Syz51cYSN9s0.js"></script>
<script src="https://sso.redhat.com//auth/js/keycloak.js"></script>
<script src="/sites/dxp-docs/files/js/js_PF3TOzXnmIprQilYYdaetKQ5CNtjKgrrHeZvPdU3fcs.js"></script>

    <!-- CP_PRIMER_HEAD -->
<meta charset="utf-8" />
<meta http-equiv="X-UA-Compatible" content="IE=edge" />
<!--[if IEMobile]><meta http-equiv="cleartype" content="on"><![endif]-->

<!-- metaInclude -->
<meta name="avalon-host-info" content="kcs05.web.prod.ext.phx2.redhat.com" />
<meta name="avalon-version" content="985a2a8f" />
<meta name="cp-chrome-build-date" content="2022-04-07T14:59:46.486Z" />

<meta name="viewport" content="width=device-width, initial-scale=1" />

<!-- Chrome, Firefox OS and Opera -->
<meta name="theme-color" content="#000000">
<!-- Windows Phone -->
<meta name="msapplication-navbutton-color" content="#000000">
<!-- iOS Safari -->
<meta name="apple-mobile-web-app-status-bar-style" content="#000000">
<link rel="manifest" href="https://access.redhat.com/webassets/avalon/j/manifest.json">
<!-- Open Search - Tap to search -->
<link rel="search" type="application/opensearchdescription+xml" title="Red Hat Customer Portal" href="https://access.redhat.com/webassets/avalon/j/opensearch.xml" />
<!-- title -->
<title>Red Hat Customer Portal - Access to 24x7 support and knowledge</title>
<!-- /title -->
<script type="text/javascript">
    window.portal = {
        analytics : {},
        host      : "https://access.redhat.com",
        idp_url   : "https://sso.redhat.com",
        lang      : "en",  
        version   : "985a2a8f",
        builddate : "2022-04-07T14:59:46.486Z",
        fetchdate : "2022-04-10T07:30:08-0400",
        nrid      : "14615289",
        nrlk      : "2a497fa56f"
    };
</script>
<script type="text/javascript">
    if (!/\/logout.*/.test(location.pathname) && portal.host === location.origin && document.cookie.indexOf('rh_sso_session') >= 0 && !(document.cookie.indexOf('rh_jwt') >= 0)) window.location = '/login?redirectTo=' + encodeURIComponent(window.location.href);
</script>
<!-- cssInclude -->

<link rel="shortcut icon" href="https://access.redhat.com/webassets/avalon/g/favicon.ico" />

<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/chrome_themes/nimbus/css/bootstrap.css?v=985a2a8f" />
<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/chrome_themes/nimbus/css/bootstrap-grid.css?v=985a2a8f" />
<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/chrome_themes/nimbus/css/main.css?v=985a2a8f" />
<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/chrome_themes/nimbus/css/components.css?v=985a2a8f" />
<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/chrome_themes/nimbus/css/pages.css?v=985a2a8f" />

<link href="https://access.redhat.com/webassets/avalon/s/chosen.css?v=985a2a8f" rel="stylesheet" type="text/css" />

<!--[if lte IE 9]>
<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/chrome_themes/nimbus/css/ie.css" />
<![endif]-->

<noscript>
    <style type="text/css" media="screen"> .primary-nav { display: block; } </style>
</noscript>
<link media="all" rel="stylesheet" type="text/css" href="https://access.redhat.com/webassets/avalon/j/public_modules/node_modules/@cpelements/pfe-navigation/dist/pfe-navigation--lightdom.min.css" />

<link rel="preload" href="https://static.redhat.com/libs/redhat/redhat-font/2/webfonts/RedHatText/RedHatText-Regular.woff" as="font" type="font/woff" crossorigin>
<link rel="preload" href="https://static.redhat.com/libs/redhat/redhat-font/2/webfonts/RedHatText/RedHatText-Medium.woff" as="font" type="font/woff" crossorigin>
<link rel="preload" href="https://static.redhat.com/libs/redhat/redhat-font/2/webfonts/RedHatDisplay/RedHatDisplay-Regular.woff" as="font" type="font/woff" crossorigin>
<link rel="preload" href="https://static.redhat.com/libs/redhat/redhat-font/2/webfonts/RedHatDisplay/RedHatDisplay-Medium.woff" as="font" type="font/woff" crossorigin>
<link rel="preload" href="https://static.redhat.com/libs/redhat/redhat-font/2/webfonts/RedHatDisplay/RedHatDisplay-Bold.woff" as="font" type="font/woff" crossorigin>

<!-- /cssInclude -->
  <!-- TrustArc -->
  <script src="//static.redhat.com/libs/redhat/marketing/latest/trustarc/trustarc.js"></script>


<script src="https://access.redhat.com/webassets/avalon/j/public_modules/node_modules/@cpelements/pfe-navigation/dist/ie-polyfills.js?v=985a2a8f"></script>

<script>
    (function () {
        if (!(window.doNotTrack == "1" || navigator.doNotTrack == "1" || navigator.msDoNotTrack == "1" || navigator.doNotTrack == "yes")) {
            var s = document.createElement("script");
            s.src="//www.redhat.com/dtm.js";
            document.head.insertBefore(s, document.head.firstElementChild);
        }
    })();
</script>

<script type="text/javascript" src="https://access.redhat.com/webassets/avalon/j/lib/require.js?v=985a2a8f" data-main="/webassets/avalon/j/"></script>

<!--[if lt IE 9]>
<script src="https://oss.maxcdn.com/html5shiv/3.7.2/html5shiv.min.js"></script>
<script src="https://oss.maxcdn.com/respond/1.4.2/respond.min.js"></script>
<script src="https://access.redhat.com/chrome_themes/nimbus/js/ie8.js"></script>
<![endif]-->
<script type="text/javascript" src="https://access.redhat.com/chrome_themes/nimbus/js/new-nav.js?v=985a2a8f" ></script>
<!-- /CP_PRIMER_HEAD -->

  </head>
  <body>
        <a href="#main-content" class="visually-hidden focusable">
      Skip to main content
    </a>
    
      <div class="dialog-off-canvas-main-canvas" data-off-canvas-main-canvas>
      <!-- CP_PRIMER_HEADER -->
<div id="page-wrap" class="page-wrap">
    <div id="pers-top-page-wrap" class="top-page-wrap pers-loader-bg">

      <div id="hero-bg-top-left" class="summit-bg-shapes"></div>
      <div id="hero-bg-top-right" class="summit-bg-shapes"></div>

        <!--googleoff: all-->
        <header class="masthead" id="masthead">

            <a href="#pfe-navigation" id="global-skip-to-nav" class="skip-link visually-hidden">Skip to navigation</a>
<a href="#cp-main" class="skip-link visually-hidden">Skip to main content</a>


 <nav id="portal-utility-nav" class="utility-navigation utility-navigation--bar hidden-at-mobile" data-analytics-region="utility">
   <h3 id="nav__utility-nav--desktop" class="element-invisible">
     Utilities
   </h3>
   <ul aria-labelledby="nav__utility-nav--desktop">
     <li id="nav-subscription" data-portal-tour-1="1">
       <a class="top-nav-subscriptions" data-analytics-level="2" data-analytics-category="Utilities" data-analytics-text="Subscription" href="https://access.redhat.com/management/" >
         Subscriptions
       </a>
     </li>
     <li id="nav-downloads" data-portal-tour-1="2">
       <a class="top-nav-downloads" data-analytics-level="2" data-analytics-category="Utilities" data-analytics-text="Downloads" href="https://access.redhat.com/downloads/" >
         Downloads
       </a>
     </li>
     <li id="nav-containers">
       <a class="top-nav-containers" data-analytics-level="2" data-analytics-category="Utilities" data-analytics-text="Containers" href="https://catalog.redhat.com/software/containers/explore/" >
         Containers
       </a>
     </li>
     <li id="nav-support" data-portal-tour-1="3">
       <a class="top-nav-support-cases" data-analytics-level="2" data-analytics-category="Utilities" data-analytics-text="Support Cases" href="https://access.redhat.com/support/cases/" >
         Support Cases
       </a>
     </li>
   </ul>
</nav>

<pfe-navigation id="pfe-navigation" data-analytics-region="mega menu">
  <div class="pfe-navigation__logo-wrapper" id="pfe-navigation__logo-wrapper">
    <a href="https://access.redhat.com/" class="pfe-navigation__logo-link" data-analytics-text="logo" data-analytics-category="MM|logo">
      <img class="pfe-navigation__logo-image" alt="Red Hat Customer Portal" src="https://access.redhat.com/chrome_themes/nimbus/img/red-hat-customer-portal.svg" />
    </a>
  </div>

  <nav class="pfe-navigation" aria-label="Main Navigation" data-analytics-region="main nav">
    <ul class="pfe-navigation__menu" id="pfe-navigation__menu">

             <li class="pfe-navigation__menu-item hidden-at-tablet hidden-at-desktop" id="nav-subscription" data-portal-tour-1="1">
        <a class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Subscription" href="https://access.redhat.com/management/" >
          Subscriptions
        </a>
      </li>
      <li class="pfe-navigation__menu-item hidden-at-tablet hidden-at-desktop" id="nav-downloads" data-portal-tour-1="2">
        <a class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Downloads" href="https://access.redhat.com/downloads/" >
          Downloads
        </a>
      </li>
      <li class="pfe-navigation__menu-item hidden-at-tablet hidden-at-desktop" id="nav-containers">
        <a class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Containers" href="https://catalog.redhat.com/software/containers/explore/" >
          Containers
        </a>
      </li>
      <li class="pfe-navigation__menu-item hidden-at-tablet hidden-at-desktop" id="nav-support" data-portal-tour-1="3">
        <a class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Support Cases" href="https://access.redhat.com/support/cases/" >
          Support Cases
        </a>
      </li>

            <li class="pfe-navigation__menu-item">
        <a href="https://access.redhat.com/products/" class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Products and Services">
          Products &amp; Services
        </a>
        <div class="pfe-navigation__dropdown has-primary-detail">
                    <div class="desktop-col-span-2 tablet-col-span-all">
            <h3>
              <a data-analytics-level="2" data-analytics-category="Products and Services" data-analytics-text="Products" href="https://access.redhat.com/products/">
                Products
              </a>
            </h3>
            <slot name="main-menu__dropdown--product__product-listing"></slot>
          </div>
                    <div>
            <h3 id="nav__products__support">
              <a data-analytics-level="2" data-analytics-category="Products and Services" data-analytics-text="Support" href="https://access.redhat.com/support">
                Support
              </a>
            </h3>
            <ul aria-labelledby="nav__products__support">
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Support" data-analytics-text="Production Support" href="https://access.redhat.com/support/offerings/production/">
                Production Support
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Support" data-analytics-text="Development Support" href="https://access.redhat.com/support/offerings/developer/">
                Development Support
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Support" data-analytics-text="Product Life Cycles" href="https://access.redhat.com/product-life-cycles/">
                Product Life Cycles
              </a></li>
            </ul>

            <h3 id="nav__products__services">
              <a data-analytics-level="2" data-analytics-category="Products and Services" data-analytics-text="Services" href="https://www.redhat.com/en/services">
                Services
              </a>
            </h3>
            <ul aria-labelledby="nav__products__services">
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Services" data-analytics-text="Consulting" href="https://www.redhat.com/en/services/consulting">
                Consulting
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Services" data-analytics-text="Technical Account Management" href="https://access.redhat.com/support/offerings/tam/">
                Technical Account Management
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Services" data-analytics-text="Training and Certifications" href="https://www.redhat.com/en/services/training-and-certification">
                Training &amp; Certifications
              </a></li>
            </ul>
          </div>

                    <div>
            <h3 id="nav__products__documentation">
              <a data-analytics-level="2" data-analytics-category="Products and Services" data-analytics-text="Documentation" href="https://access.redhat.com/documentation">
                Documentation
              </a>
            </h3>
            <ul aria-labelledby="nav__products__documentation">
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Documentation" data-analytics-text="Red Hat Enterprise Linux" href="https://access.redhat.com/documentation/en/red_hat_enterprise_linux">
                Red Hat Enterprise Linux
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Documentation" data-analytics-text="Red Hat JBoss Enterprise Application Platform" href="https://access.redhat.com/documentation/en/red_hat_jboss_enterprise_application_platform">
                Red Hat JBoss Enterprise Application Platform
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Documentation" data-analytics-text="Red Hat OpenStack Platform" href="https://access.redhat.com/documentation/en/red_hat_openstack_platform">
                Red Hat OpenStack Platform
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Documentation" data-analytics-text="Red Hat OpenShift Container Platform" href="https://access.redhat.com/documentation/en/openshift_container_platform">
                Red Hat OpenShift Container Platform
              </a></li>
            </ul>
            <pfe-cta>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Documentation" data-analytics-text="All Documentation" data-analytics-linkType="cta" href="https://access.redhat.com/documentation">
                All Documentation
              </a>
            </pfe-cta>

            <h3 id="nav__products__catalog"><a data-analytics-level="2" data-analytics-category="Products and Services" data-analytics-text="Ecosystem Catalog" href="https://catalog.redhat.com/">
              Ecosystem Catalog
            </a></h3>
            <ul aria-labelledby="nav__products__catalog">
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Ecosystem Catalog" data-analytics-text="Red Hat in the Public Cloud" href="https://access.redhat.com/public-cloud">
                Red Hat in the Public Cloud
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Products and Services|Ecosystem Catalog" data-analytics-text="Partner Resources" href="https://access.redhat.com/ecosystem/partner-resources">
                Partner Resources
              </a></li>
            </ul>
          </div>

        </div>
      </li>

            <li class="pfe-navigation__menu-item">
        <a class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Tools" href="https://access.redhat.com/labs/">
          Tools
        </a>
        <div class="pfe-navigation__dropdown pfe-navigation__dropdown--3-column">
                    <div>
            <h3 id="nav__tools__tools" data-analytics-level="2" data-analytics-text="Tools" data-analytics-category="Tools">
              Tools
            </h3>
            <ul aria-labelledby="nav__tools__tools">
                <li><a data-analytics-level="3" data-analytics-category="Tools|Tools" data-analytics-text="Solution Engine" href="https://access.redhat.com/support/cases/#/troubleshoot">
                  Troubleshoot a product issue
                </a></li>
                <li><a data-analytics-level="3" data-analytics-category="Tools|Tools" data-analytics-text="Packages" href="https://access.redhat.com/downloads/content/package-browser">
                  Packages
                </a></li>
                <li><a data-analytics-level="3" data-analytics-category="Tools|Tools" data-analytics-text="Errata" href="https://access.redhat.com/errata/">
                  Errata
                </a></li>
            </ul>
          </div>

                    <div>
            <h3 id="nav__tools__labs">
              <a data-analytics-level="2" data-analytics-category="Tools" data-analytics-text="Customer Portal Labs" href="https://access.redhat.com/labs/">
                Customer Portal Labs
              </a>
            </h3>
            <ul aria-labelledby="nav__tools__labs">
              <li><a data-analytics-level="3" data-analytics-category="Tools|Customer Portal Labs" data-analytics-text="Configuration" href="https://access.redhat.com/labs/#!?type=config">
                Configuration
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Tools|Customer Portal Labs" data-analytics-text="Deployment" href="https://access.redhat.com/labs/#!?type=deploy">
                Deployment
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Tools|Customer Portal Labs" data-analytics-text="Security" href="https://access.redhat.com/labs/#!?type=security">
                Security
              </a></li>
                            <li><a data-analytics-level="3" data-analytics-category="Tools|Customer Portal Labs" data-analytics-text="Troubleshooting" href="https://access.redhat.com/labs/#!?type=troubleshoot">
                Troubleshoot
              </a></li>
            </ul>
            <pfe-cta>
              <a data-analytics-level="3" data-analytics-category="Tools|Customer Portal Labs" data-analytics-text="All Labs" data-analytics-linkType="cta" href="https://access.redhat.com/labs/">
                All labs
              </a>
            </pfe-cta>
          </div>

                    <div>
            <h4 id="nav__tools__red-hat-insights">
              <a data-analytics-level="2" data-analytics-category="Tools" data-analytics-text="Red Hat Insights" href="//www.redhat.com/en/technologies/management/insights">
                Red Hat Insights
              </a>
            </h4>
            <p>Increase visibility into IT operations to detect and resolve technical issues before they impact your business.</p>
            <a data-analytics-level="3" data-analytics-category="Tools|Red Hat Insights" data-analytics-text="Learn more" href="https://www.redhat.com/en/technologies/management/insights">
              Learn More
            </a>
            <br>
            <a data-analytics-level="3" data-analytics-category="Tools|Red Hat Insights" data-analytics-text="Go to Insights" href="https://cloud.redhat.com/insights">
              Go to Insights
            </a>
          </div>
        </div>
      </li>

            <li class="pfe-navigation__menu-item">
        <a class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Security" href="https://access.redhat.com/security/">
          Security
        </a>
        <div class="pfe-navigation__dropdown pfe-navigation__dropdown--3-column">
                    <div>
            <h3 id="security__security-center">
              <a data-analytics-level="2" data-analytics-category="Security" data-analytics-text="Red Hat Product Security Center" href="https://access.redhat.com/security">
                Red Hat Product Security Center
              </a>
            </h3>
            <p>
              Engage with our Red Hat Product Security team, access security updates, and ensure your environments are not exposed to any known security vulnerabilities.
            </p>
            <pfe-cta pfe-priority="primary">
              <a data-analytics-level="3" data-analytics-category="Security|Red Hat Product Security Center" data-analytics-text="Product Security Center" data-analytics-linkType="cta" href="https://access.redhat.com/security/">
                Product Security Center
              </a>
            </pfe-cta>
          </div>
                    <div>
            <h3 id="nav__security__updates" data-analytics-level="2" data-analytics-text="Security Updates" data-analytics-category="Security">
              <a data-analytics-level="2" data-analytics-category="Security" data-analytics-text="Security Updates" href="/security">
                Security Updates
              </a>
            </h3>
            <ul aria-labelledby="nav__security__updates">
              <li><a data-analytics-level="3" data-analytics-category="Security|Security Updates" data-analytics-text="Security Advisories" href="https://access.redhat.com/security/security-updates/#/security-advisories">
                Security Advisories
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Security|Security Updates" data-analytics-text="Red Hat CVE Database" href="https://access.redhat.com/security/security-updates/#/cve">
                Red Hat CVE Database
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Security|Security Updates" data-analytics-text="Security Labs" href="https://access.redhat.com/security/security-updates/#/security-labs">
                Security Labs
              </a></li>
            </ul>
            <p class="margin-top-xl">
              Keep your systems secure with Red Hat&#039;s specialized responses to security vulnerabilities.
            </p>
            <pfe-cta>
              <a data-analytics-level="3" data-analytics-category="Security|Security Updates" data-analytics-text="View Responses" data-analytics-linkType="cta" href="https://access.redhat.com/security/vulnerability">
                View Responses
              </a>
            </pfe-cta>
          </div>

                    <div>
            <h3 id="nav__security__resources">
              <a data-analytics-level="2" data-analytics-category="Security" data-analytics-text="Resources" href="https://access.redhat.com/security/overview">
                Resources
              </a>
            </h3>
            <ul aria-labelledby="nav__security__resources">
                            <li><a data-analytics-level="3" data-analytics-category="Security|Resources" data-analytics-text="Security Blog" href="//redhat.com/en/blog/channel/security">
                Security Blog
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Security|Resources" data-analytics-text="Security Measurement" href="https://www.redhat.com/security/data/metrics/">
                Security Measurement
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Security|Resources" data-analytics-text="Severity Ratings" href="https://access.redhat.com/security/updates/classification/">
                Severity Ratings
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Security|Resources" data-analytics-text="Backporting Policies" href="https://access.redhat.com/security/updates/backporting/">
                Backporting Policies
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Security|Resources" data-analytics-text="Product Signing (GPG) Keys" href="https://access.redhat.com/security/team/key/">
                Product Signing (GPG) Keys
              </a></li>
            </ul>
          </div>

        </div>
      </li>

            <li class="pfe-navigation__menu-item">
        <a href="https://access.redhat.com/community/" class="pfe-navigation__menu-link" data-analytics-level="1" data-analytics-text="Community">
          Community
        </a>
        <div class="pfe-navigation__dropdown pfe-navigation__dropdown--3-column">

                    <div>
            <h3 id="nav__community__cp-community">
              <a href="https://access.redhat.com/community" data-analytics-level="2" data-analytics-text="Customer Portal Community" data-analytics-text="Customer Portal Community" data-analytics-category="Community">
                Customer Portal Community
              </a>
            </h3>
            <ul aria-labelledby="nav__community__cp-community">
              <li><a data-analytics-level="3" data-analytics-category="Community|Customer Portal Community" data-analytics-text="Discussions" href="https://access.redhat.com/discussions">
                Discussions
              </a></li>
                            <li><a data-analytics-level="3" data-analytics-category="Community|Customer Portal Community" data-analytics-text="Private Groups" href="https://access.redhat.com/groups/">
                Private Groups
              </a></li>
            </ul>

            <pfe-cta pfe-priority="primary">
              <a data-analytics-level="3" data-analytics-category="Community|Customer Portal Community" data-analytics-text="Community Activity" data-analytics-linkType="cta" href="https://access.redhat.com/community/">
                Community Activity
              </a>
            </pfe-cta>
          </div>

                    <div>
            <h3 id="nav__community__events" data-analytics-level="2" data-analytics-text="Customer Events" data-analytics-category="Community">
              Customer Events
            </h3>
            <ul aria-labelledby="nav__community__events">
              <li><a data-analytics-level="3" data-analytics-category="Community|Customer Events" data-analytics-text="Red Hat Convergence" href="https://access.redhat.com/convergence/">
                Red Hat Convergence
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Community|Customer Events" data-analytics-text="Red Hat Summit" href="http://www.redhat.com/summit/">
                Red Hat Summit
              </a></li>
            </ul>
          </div>

                    <div>
            <h3 id="nav__community__stories" data-analytics-level="2" data-analytics-text="Stories" data-analytics-category="Community">
              Stories
            </h3>
            <ul aria-labelledby="nav__community__stories">
              <li><a data-analytics-level="3" data-analytics-category="Community|Stories" data-analytics-text="Red Hat Subscription Value" href="https://access.redhat.com/subscription-value/">
                Red Hat Subscription Value
              </a></li>
              <li><a data-analytics-level="3" data-analytics-text="You Asked. We Acted." data-analytics-category="Community|Stories" href="https://access.redhat.com/you-asked-we-acted/">
                You Asked. We Acted.
              </a></li>
              <li><a data-analytics-level="3" data-analytics-category="Community|Stories" data-analytics-text="Open Source Communities" href="http://www.redhat.com/en/open-source">
                Open Source Communities
              </a></li>
            </ul>
          </div>
        </div>
      </li>
    </ul>



        </nav>

    <div id="site-search" slot="search" class="utility-link site-search">
    <div class="content">
      <form class="ng-pristine ng-valid topSearchForm" id="topSearchForm" name="topSearchForm" action="/search/browse/search/" method="get" enctype="application/x-www-form-urlencoded">
        <cp-search-autocomplete class="push-bottom" path="/webassets/avalon/j/data.json"></cp-search-autocomplete>
                <div>
          Or <a href="/support/cases/#/troubleshoot">troubleshoot an issue</a>.
        </div>
      </form>
    </div>
  </div>


  <div slot="secondary-links" id="localesMenu">
    <button class="pfe-navigation__secondary-link">
      <pfe-icon icon="web-icon-globe" size="sm" aria-hidden="true"></pfe-icon>
      English
    </button>

    <pfe-navigation-dropdown dropdown-width="single">
      <h2 class="utility-header">
        Select Your Language
      </h2>
      <ul class="reset">
        <li><a href="https://access.redhat.com/changeLanguage?language=en" data-lang="en" id="en" data-analytics-text="English">English</a></li>
        <li><a href="https://access.redhat.com/changeLanguage?language=ko" data-lang="ko" id="ko" data-analytics-text="Korean">한국어</a></li>
        <li><a href="https://access.redhat.com/changeLanguage?language=ja"    data-lang="ja"    id="ja" data-analytics-text="Japanese">日本語</a></li>
        <li><a href="https://access.redhat.com/changeLanguage?language=zh_CN" data-lang="zh_CN" id="zh_CN" data-analytics-text="Chinese">中文 (中国)</a></li>
      </ul>

    </pfe-navigation-dropdown>
  </div>

    <rh-account-dropdown slot="account"></rh-account-dropdown>

    <pfe-primary-detail breakpoint-width="600" class="main-menu__dropdown--product__product-listing" slot="main-menu__dropdown--product__product-listing" consistent-height>
    <h3 slot="details-nav">
              Infrastructure and Management
          </h3>
    <div slot="details">
      <ul>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Enterprise Linux" href="https://access.redhat.com/products/red-hat-enterprise-linux/">
                Red Hat Enterprise Linux
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Virtualization" href="https://access.redhat.com/products/red-hat-virtualization/">
                Red Hat Virtualization
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Identity Management" href="https://access.redhat.com/products/identity-management/">
                Red Hat Identity Management
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Directory Server" href="https://access.redhat.com/products/red-hat-directory-server/">
                Red Hat Directory Server
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Certificate System" href="https://access.redhat.com/products/red-hat-certificate-system/">
                Red Hat Certificate System
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Satellite" href="https://access.redhat.com/products/red-hat-satellite/">
                Red Hat Satellite
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Subscription Management" href="https://access.redhat.com/products/red-hat-subscription-management/">
                Red Hat Subscription Management
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Update Infrastructure" href="https://access.redhat.com/products/red-hat-update-infrastructure/">
                Red Hat Update Infrastructure
              </a>
          </li>
          <li>
              <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Insights" href="https://access.redhat.com/products/red-hat-insights/">
                Red Hat Insights
              </a>
          </li>
        <li><a data-analytics-level="3" data-analytics-category="Products and Services|Products:Infrastructure and Management" data-analytics-text="Red Hat Ansible Automation Platform" href="https://access.redhat.com/products/red-hat-ansible-automation-platform/">
          Red Hat Ansible Automation Platform
        </a></li>
      </ul>
    </div>

    <h3 slot="details-nav">
              Cloud Computing
          </h3>
    <div slot="details">
      <ul>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat OpenShift" href="https://access.redhat.com/products/openshift">
            Red Hat OpenShift
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat CloudForms" href="https://access.redhat.com/products/red-hat-cloudforms/">
            Red Hat CloudForms
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat OpenStack Platform" href="https://access.redhat.com/products/red-hat-openstack-platform/">
            Red Hat OpenStack Platform
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing Platform" data-analytics-text="Red Hat OpenShift Container Platform" href="https://access.redhat.com/products/red-hat-openshift-container-platform/">
            Red Hat OpenShift Container Platform
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing Platform" data-analytics-text="Red Hat OpenShift Data Science" href="https://access.redhat.com/products/red-hat-openshift-data-science/">
            Red Hat OpenShift Data Science
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat OpenShift Online" href="https://access.redhat.com/products/openshift-online-red-hat/">
            Red Hat OpenShift Online
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat OpenShift Dedicated" href="https://access.redhat.com/products/openshift-dedicated-red-hat/">
            Red Hat OpenShift Dedicated
          </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing Platform" data-analytics-text="Red Hat Advanced Cluster Security for Kubernetes" href="https://access.redhat.com/products/red-hat-advanced-cluster-security-for-kubernetes/">
                Red Hat Advanced Cluster Security for Kubernetes
            </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat Advanced Cluster Management for Kubernetes" href="https://access.redhat.com/products/red-hat-advanced-cluster-management-for-kubernetes/">
            Red Hat Advanced Cluster Management for Kubernetes
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat Quay" href="https://access.redhat.com/products/red-hat-quay/">
            Red Hat Quay
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat CodeReady Workspaces" href="https://access.redhat.com/products/red-hat-codeready-workspaces/">
            Red Hat CodeReady Workspaces
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Cloud Computing" data-analytics-text="Red Hat OpenShift Service on AWS" href="https://access.redhat.com/products/red-hat-openshift-service-aws">
            Red Hat OpenShift Service on AWS
          </a>
        </li>
      </ul>
    </div>

    <h3 slot="details-nav">
              Storage
          </h3>
    <div slot="details">
      <ul>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Storage" data-analytics-text="Red Hat Gluster Storage" href="https://access.redhat.com/products/red-hat-storage/">
              Red Hat Gluster Storage
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Storage" data-analytics-text="Red Hat Hyperconverged Infrastructure" href="https://access.redhat.com/products/red-hat-hyperconverged-infrastructure/">
              Red Hat Hyperconverged Infrastructure
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Storage" data-analytics-text="Red Hat Ceph Storage" href="https://access.redhat.com/products/red-hat-ceph-storage/">
              Red Hat Ceph Storage
            </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Storage" data-analytics-text="Red Hat Openshift Container Storage" href="https://access.redhat.com/products/red-hat-openshift-data-foundation">
            Red Hat OpenShift Data Foundation
          </a>
        </li>
      </ul>
    </div>

    <h3 slot="details-nav">
              Runtimes
          </h3>
    <div slot="details">
      <ul>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat Runtimes" href="https://access.redhat.com/products/red-hat-runtimes/">
              Red Hat Runtimes
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat JBoss Enterprise Application Platform" href="https://access.redhat.com/products/red-hat-jboss-enterprise-application-platform/">
              Red Hat JBoss Enterprise Application Platform
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat Data Grid" href="https://access.redhat.com/products/red-hat-data-grid/">
              Red Hat Data Grid
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat JBoss Web Server" href="https://access.redhat.com/products/red-hat-jboss-web-server/">
              Red Hat JBoss Web Server
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat Single Sign On" href="https://access.redhat.com/products/red-hat-single-sign-on/">
              Red Hat Single Sign On
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat support for Spring Boot" href="https://access.redhat.com/products/spring-boot/">
              Red Hat support for Spring Boot
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat build of Node.js" href="https://access.redhat.com/products/nodejs/">
              Red Hat build of Node.js
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat build of Thorntail" href="https://access.redhat.com/products/thorntail/">
              Red Hat build of Thorntail
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat build of Eclipse Vert.x" href="https://access.redhat.com/products/eclipse-vertx/">
              Red Hat build of Eclipse Vert.x
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat build of OpenJDK" href="https://access.redhat.com/products/openjdk/">
              Red Hat build of OpenJDK
            </a>
        </li>
                <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat build of Quarkus" href="https://access.redhat.com/products/quarkus/">
              Red Hat build of Quarkus
            </a>
        </li>
        <li>
            <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Runtimes" data-analytics-text="Red Hat CodeReady Studio" href="https://access.redhat.com/products/red-hat-codeready-studio/">
              Red Hat CodeReady Studio
            </a>
        </li>
      </ul>
    </div>

    <h3 slot="details-nav">
              Integration and Automation
          </h3>
    <div slot="details">
      <ul class="border-bottom" id="portal-menu-border-bottom">
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat Integration" href="https://access.redhat.com/products/red-hat-integration/">
            Red Hat Integration
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat Fuse" href="https://access.redhat.com/products/red-hat-fuse/">
            Red Hat Fuse
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat AMQ" href="https://access.redhat.com/products/red-hat-amq/">
            Red Hat AMQ
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat 3scale API Management" href="https://access.redhat.com/products/red-hat-3scale/">
            Red Hat 3scale API Management
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat JBoss Data Virtualization" href="https://access.redhat.com/products/red-hat-jboss-data-virtualization/">
            Red Hat JBoss Data Virtualization
          </a>
        </li>
      </ul>
      <ul>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat Process Automation" href="https://access.redhat.com/products/red-hat-process-automation/">
            Red Hat Process Automation
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat Process Automation Manager" href="https://access.redhat.com/products/red-hat-process-automation-manager/">
            Red Hat Process Automation Manager
          </a>
        </li>
        <li>
          <a data-analytics-level="3" data-analytics-category="Products and Services|Products:Integration and Automation" data-analytics-text="Red Hat Decision Manager" href="https://access.redhat.com/products/red-hat-decision-manager/">
            Red Hat Decision Manager
          </a>
        </li>
      </ul>
    </div>
    <div slot="details-nav--footer">
      <pfe-cta pfe-priority="primary">
        <a href="https://access.redhat.com/products/" class="pfe-navigation__menu-link" data-analytics-level="2" data-analytics-text="All Products" data-analytics-category="Products and Services|Products:" data-analytics-linkType="cta">
          All Products
        </a>
      </pfe-cta>
    </div>
  </pfe-primary-detail>

  <div slot="secondary-links" class="pfe-navigation__site-switcher">
    <button class="pfe-navigation__secondary-link">
      <pfe-icon icon="web-icon-grid-3x3" size="sm" aria-hidden="true"></pfe-icon>
      All Red Hat
    </button>
    <pfe-navigation-dropdown dropdown-width="full">
      <site-switcher></site-switcher>
    </pfe-navigation-dropdown>
  </div>

</pfe-navigation>

<div id="scroll-anchor"></div>
            <!--[if IE 8]>
            <div class="portal-messages">
                <div class="alert alert-warning alert-portal alert-w-icon">
                    <span class="icon-warning alert-icon" aria-hidden="true"></span>
                    You are using an unsupported web browser. Update to a supported browser for the best experience. <a href="/announcements/2120951">Read the announcement</a>.
                </div>
            </div>
            <![endif]-->
            <!--[if IE 9]>
            <div class="portal-messages">
                <div class="alert alert-warning alert-portal alert-w-icon">
                    <span class="icon-warning alert-icon" aria-hidden="true"></span>
                    As of March 1, 2016, the Red Hat Customer Portal will no longer support Internet Explorer 9. See our new <a href="/help/browsers">browser support policy</a> for more information.
                </div>
            </div>
            <![endif]-->
            <div id="site-section"></div>
        </header>
        <!--googleon: all-->

        <main id="cp-main" class="portal-content-area">
            <div id="cp-content" class="main-content">
<!-- /CP_PRIMER_HEADER -->

      <div class="container">
        

                                                                                                        <script>breadcrumbs = [["Products & Services","\/products\/"],["Product Documentation","\/documentation"],["Red Hat Ceph Storage","\/documentation\/en-us\/red_hat_ceph_storage"],["2","\/documentation\/en-us\/red_hat_ceph_storage\/2"],["Administration Guide","\/documentation\/en-us\/red_hat_ceph_storage\/2\/html\/administration_guide"],["Chapter\u00a08.\u00a0Adding and Removing OSD Nodes","\/documentation\/en-us\/red_hat_ceph_storage\/2\/html\/administration_guide\/adding_and_removing_osd_nodes"]]</script>

<div data-drupal-messages-fallback class="hidden"></div>


    </div>
        <div class="container">
        

    <article class="rh_docs">
    <div class="container">
      <div class="row">
        <div itemscope="" itemtype="https://schema.org/TechArticle" itemref="techArticle-md1 techArticle-md2 techArticle-md3"></div>
        <div itemscope="" itemtype="https://schema.org/SoftwareApplication" itemref="softwareApplication-md1 softwareApplication-md2 softwareApplication-md3 softwareApplication-md4"></div>
                  

  <a class="toc-toggle toc-show affix-top" data-toggle="collapse" data-target="#toc-main" aria-expanded="false" aria-controls="toc-main">
  <span class="sr-only">Show Table of Contents</span>
  <span class="web-icon-mobile-menu" aria-hidden="true"></span>
</a>
<nav id="toc-main" class="toc-main collapse in">
  <div class="toc-menu affix-top">
    <a class="toc-toggle toc-hide" data-toggle="collapse" data-target="#toc-main" aria-expanded="false" aria-controls="toc-main">
      <span class="sr-only">Hide Table of Contents</span>
      <span class="icon-remove" aria-hidden="true"></span>
    </a>
    <div class="doc-options">
      <div class="doc-language btn-group">
        <button type="button" class="btn btn-app dropdown-toggle" data-toggle="dropdown" aria-expanded="false">
          English <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu">
                      <li>
              <a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/index">English</a>
            </li>
                  </ul>
      </div>
      <div class="doc-format btn-group">
        <button type="button" class="btn btn-app dropdown-toggle" data-toggle="dropdown" aria-expanded="false">
          Multi-page HTML <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu">
                      <li><a href="/documentation/en-us/red_hat_ceph_storage/2/html-single/administration_guide">Single-page HTML</a></li>
                      <li><a href="/documentation/en-us/red_hat_ceph_storage/2/pdf/administration_guide/Red_Hat_Ceph_Storage-2-Administration_Guide-en-US.pdf">PDF</a></li>
                      <li><a href="/documentation/en-us/red_hat_ceph_storage/2/epub/administration_guide/Red_Hat_Ceph_Storage-2-Administration_Guide-en-US.epub">ePub</a></li>
                  </ul>
      </div>
    </div>
          <ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/index">Administration Guide</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/overview">1. Overview</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/process_management">2. Process Management</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/process_management#running_ceph_as_a_systemd_service">2.1. Running Ceph as a systemd Service</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/process_management#starting_stopping_restarting_all_daemons">2.1.1. Starting, Stopping, Restarting All Daemons</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/process_management#starting_stopping_restarting_all_daemons_by_type">2.1.2. Starting, Stopping, Restarting All Daemons by Type</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/process_management#starting_stopping_restarting_a_daemon_by_instances">2.1.3. Starting, Stopping, Restarting a Daemon by Instances</a></li></ol></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring">3. Monitoring</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#high_level_monitoring">3.1. High-level Monitoring</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#interactive_mode">3.1.1. Interactive Mode</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#checking_cluster_health">3.1.2. Checking Cluster Health</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#watching_a_cluster">3.1.3. Watching a Cluster</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#checking_a_cluster_s_usage_statistics">3.1.4. Checking a Cluster’s Usage Statistics</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#checking_a_cluster_s_status">3.1.5. Checking a Cluster’s Status</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#checking_monitor_status">3.1.6. Checking Monitor Status</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#using_the_administration_socket">3.1.7. Using the Administration Socket</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#checking_osd_status">3.1.8. Checking OSD Status</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#low_level_monitoring">3.2. Low-level Monitoring</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#placement_group_sets">3.2.1. Placement Group Sets</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#peering-2">3.2.2. Peering</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#monitoring_placement_group_states">3.2.3. Monitoring Placement Group States</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#creating-1">3.2.3.1. Creating</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#peering_2">3.2.3.2. Peering</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#active-1">3.2.3.3. Active</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#clean-1">3.2.3.4. Clean</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#degraded-1">3.2.3.5. Degraded</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#recovering-1">3.2.3.6. Recovering</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#backfilling">3.2.3.7. Backfilling</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#remapped-1">3.2.3.8. Remapped</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#stale-1">3.2.3.9. Stale</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#misplaced-1">3.2.3.10. Misplaced</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#incomplete-1">3.2.3.11. Incomplete</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#identifying_troubled_placement_groups">3.2.4. Identifying Troubled Placement Groups</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#finding_an_object_location">3.2.5. Finding an Object Location</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#monitoring-ceph-clusters-with-the-red-hat-ceph-storage-dashboard">3.3. Monitoring Ceph Clusters with the Red Hat Ceph Storage Dashboard</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#about-the-red-hat-ceph-storage-dashboard">3.3.1. About the Red Hat Ceph Storage Dashboard</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#installing-the-red-hat-ceph-storage-dashboard">3.3.2. Installing the Red Hat Ceph Storage Dashboard</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#accessing-the-red-hat-ceph-storage-dashboard">3.3.3. Accessing the Red Hat Ceph Storage Dashboard</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#changing-the-default-red-hat-ceph-storage-dashboard-password">3.3.4. Changing the Default Red Hat Ceph Storage Dashboard Password</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#the-red-hat-ceph-storage-dashboard-alerts">3.3.5. The Red Hat Ceph Storage Dashboard Alerts</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#prerequisites_4">3.3.5.1. Prerequisites</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#about-alerts">3.3.5.2. About Alerts</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#accessing-the-alert-status-dashboard">3.3.5.3. Accessing the Alert Status Dashboard</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#configuring-the-notification-target">3.3.5.4. Configuring the Notification Target</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#changing-the-default-alerts-and-adding-new-ones">3.3.5.5. Changing the Default Alerts and Adding New Ones</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/monitoring#additional_resources_3">3.3.6. Additional Resources</a></li></ol></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/overrides">4. Overrides</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/overrides#setting_and_unsetting_overrides">4.1. Setting and Unsetting Overrides</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/overrides#use_cases">4.2. Use Cases</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management">5. User Management</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#background">5.1. Background</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#user">5.1.1. User</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#authorization_capabilities">5.1.2. Authorization (Capabilities)</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#pool">5.1.3. Pool</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#namespace">5.1.4. Namespace</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#managing_users">5.2. Managing Users</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#list_users">5.2.1. List Users</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#get_a_user">5.2.2. Get a User</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#add_a_user">5.2.3. Add a User</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#modify_user_capabilities">5.2.4. Modify User Capabilities</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#delete_a_user">5.2.5. Delete a User</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#print_a_user_s_key">5.2.6. Print a User’s Key</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#import_a_user">5.2.7. Import a User</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#keyring_management">5.3. Keyring Management</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#create_a_keyring">5.3.1. Create a Keyring</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#add_a_user_to_a_keyring">5.3.2. Add a User to a Keyring</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#create_a_user">5.3.3. Create a User</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#modify_a_user">5.3.4. Modify a User</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#command_line_usage">5.4. Command Line Usage</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/user_management#limitations">5.5. Limitations</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size">6. Managing Cluster Size</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#adding_a_monitor">6.1. Adding a Monitor</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#configuring_a_host">6.1.1. Configuring a Host</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#adding_a_monitor_with_ansible">6.1.2. Adding a Monitor with Ansible</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#adding_a_monitor_with_the_command_line_interface">6.1.3. Adding a Monitor with the Command Line Interface</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#removing_a_monitor">6.2. Removing a Monitor</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#removing_a_monitor_with_the_command_line_interface">6.2.1. Removing a Monitor with the Command Line Interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#removing_monitors_from_an_unhealthy_cluster">6.2.2. Removing Monitors from an Unhealthy Cluster</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#adding_an_osd">6.3. Adding an OSD</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#configuring_a_host_2">6.3.1. Configuring a Host</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#adding_an_osd_with_ansible">6.3.2. Adding an OSD with Ansible</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#adding_an_osd_with_the_command_line_interface">6.3.3. Adding an OSD with the Command Line Interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#observing_data_migration">6.3.4. Observing Data Migration</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#removing_an_osd">6.4. Removing an OSD</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/managing_cluster_size#removing_an_osd_with_the_command_line_interface">6.4.1. Removing an OSD with the Command Line Interface</a></li></ol></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/changing_an_osd_drive">7. Changing an OSD Drive</a></li><li class="leaf active"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes">8. Adding and Removing OSD Nodes</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes#performance_factors">8.1. Performance Factors</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes#recommendations">8.2. Recommendations</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes#removing_a_node">8.3. Removing a Node</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/adding_and_removing_osd_nodes#adding_a_node">8.4. Adding a Node</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/benchmarking_performance">9. Benchmarking Performance</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/benchmarking_performance#performance_baseline">9.1. Performance Baseline</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/benchmarking_performance#storage_cluster">9.2. Storage Cluster</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/benchmarking_performance#block_device">9.3. Block Device</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters">10. Performance Counters</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#access">10.1. Access</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#schema">10.2. Schema</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#dump">10.3. Dump</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#average_count_and_sum">10.3.1. Average Count and Sum</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#monitor_metrics_description_tables">10.3.2. Monitor Metrics Description Tables</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#osd_metrics_description_tables">10.3.3. OSD Metrics Description Tables</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/performance_counters#the_ceph_object_gateway_metrics_tables">10.3.4. The Ceph Object Gateway Metrics Tables</a></li></ol></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/osd_bluestore_technology_preview">11. OSD BlueStore (Technology Preview)</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/legal-notice">Legal Notice</a></li></ol>
      </div>
</nav>


                          <div class="doc-wrapper">
            

  <div class="card card-light card-md push-bottom">
  <h2 class="card-heading card-heading-red card-heading-sm card-heading-flush">Red Hat Training</h2>
  <p>A Red Hat training course is available for <a href="https://www.redhat.com/en/services/training/ceph125-red-hat-ceph-storage-architecture-and-administration/?intcmp=701f2000001D4RsAAK&amp;" class="cta-link">Red Hat Ceph Storage</a></p>
</div>



  <div class="pane-page-title">
    <h1 class="title" itemprop="name">Chapter 8. Adding and Removing OSD Nodes</h1>
  </div>


  <section class="chapter" id="adding_and_removing_osd_nodes"><p id="add-rm-osd-nodes">
			One of the outstanding features of Ceph is the ability to add or remove Ceph OSD nodes at run time. This means you can resize cluster capacity or replace hardware without taking down the storage cluster. The ability to serve Ceph clients while the cluster is in a <code class="literal">degraded</code> state also has operational benefits, for example, you can add or remove or replace hardware during regular business hours, rather than working overtime or weekends.
		</p><p>
			However, adding and removing Ceph OSD nodes can have a significant impact on performance, and you should consider the performance impact of adding, removing or replacing hardware on the storage cluster before you act.
		</p><p>
			From a capacity perspective, removing a node removes the OSDs contained within the node and effectively reduces the capacity of the storage cluster. Adding a node adds the OSDs contained within the node, and effectively expands the capacity of the storage cluster. Whether you are expanding or contracting cluster capacity, adding or removing Ceph OSD nodes will induce backfilling as the cluster rebalances. During that rebalancing time period, Ceph uses additional resources which can impact cluster performance.
		</p><p>
			The following diagram contains Ceph nodes where each node has four OSDs. In a storage cluster of four nodes, with 16 OSDs, removing a node removes 4 OSDs and cuts capacity by 25%. In a storage cluster of three nodes, with 12 OSDs, adding a node adds 4 OSDs and increases capacity by 33%.
		</p><div class="informalfigure"><div class="mediaobject"><img src="https://access.redhat.com/webassets/avalon/d/Red_Hat_Ceph_Storage-2-Administration_Guide-en-US/images/fbcd08a0c898f90f9f1f5f845a23b961/diag-9412ab0e7aff62ef6d529f2cd39cb88d.png" alt="diag 9412ab0e7aff62ef6d529f2cd39cb88d"/></div></div><p>
			In a production Ceph storage cluster, a Ceph OSD node has a particular hardware configuration that facilitates a particular type of storage strategy. See the Red Hat Ceph Storage <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/storage-strategies-guide/">Strategies Guide</a> for more details.
		</p><p>
			Since a Ceph OSD node is part of a CRUSH hierarchy, the performance impact of adding or removing a node typically affects the performance of pools that use that CRUSH hierarchy, that is, the CRUSH ruleset.
		</p><section class="section" id="performance_factors"><div class="titlepage"><div><div><h2 class="title">8.1. Performance Factors</h2></div></div></div><p id="add-rm-osd-nodes-perf-factors">
				The following factors typically have an impact on cluster performance when adding or removing Ceph OSD nodes:
			</p><div class="orderedlist"><ol class="orderedlist" type="1"><li class="listitem">
						<span class="strong strong"><strong>Current Client Load on Affected Pools:</strong></span> Ceph clients place load on the I/O interface to the Ceph cluster; namely, a pool. A pool maps to a CRUSH ruleset. The underlying CRUSH hierarchy allows Ceph to place data across failure domains. If the underlying Ceph OSD node involves a pool under high client loads, the client load may have a significant impact on recovery time and impact performance. More specifically, since write operations require data replication for durability, write-intensive client loads will increase the time for the cluster to recover.
					</li><li class="listitem">
						<span class="strong strong"><strong>Capacity Added or Removed:</strong></span> Generally, the capacity you are adding or removing as a percentage of the overall cluster will have an impact on the cluster’s time to recover. Additionally, the storage density of the node you add or remove may have an impact on the time to recover for example, a node with 36 OSDs will typically take longer to recover compared to a node with 12 OSDs. When removing nodes, you MUST ensure that you have sufficient spare capacity so that you will not reach the <code class="literal">full ratio</code> or <code class="literal">near full ratio</code>. If the storage cluster reaches the <code class="literal">full ratio</code>, Ceph will suspend write operations to prevent data loss.
					</li><li class="listitem">
						<span class="strong strong"><strong>Pools and CRUSH Ruleset:</strong></span> A Ceph OSD node maps to at least one Ceph CRUSH hierarchy, and the hierarchy maps to at least one pool. Each pool that uses the CRUSH hierarchy (ruleset) where you add or remove a Ceph OSD node will experience a performance impact.
					</li><li class="listitem">
						<span class="strong strong"><strong>Pool Type and Durability:</strong></span> Replication pools tend to use more network bandwidth to replicate deep copies of the data, whereas erasure coded pools tend to use more CPU to calculate <code class="literal">k+m</code> coding chunks. The more copies of the data, for example, the size or the more <code class="literal">k+m</code> chunks, the longer it will take for the cluster to recover.
					</li><li class="listitem">
						<span class="strong strong"><strong>Total Throughput Characteristics:</strong></span> Drives, controllers and network interface cards all have throughput characteristics that may impact the recovery time. Generally, nodes with higher throughput characteristics, for example, 10 Gbps and SSDs will recover faster than nodes with lower throughput characteristics, for example, 1 Gbps and SATA drives.
					</li></ol></div></section><section class="section" id="recommendations"><div class="titlepage"><div><div><h2 class="title">8.2. Recommendations</h2></div></div></div><p id="add-rm-osd-nodes-recommendations">
				The failure of a node may preclude removing one OSD at a time before changing the node. When circumstances allow you to reduce any negative performance impact when adding or removing Ceph OSD nodes, we recommend adding or removing one OSD at a time within a node and allowing the cluster to recover before proceeding to the next OSD. For details on removing an OSD, see <a class="xref" href="managing_cluster_size#removing-osds-manual">Section 6.4.1, “Removing an OSD with the Command Line Interface”</a>. When adding a Ceph node, we also recommend adding one OSD at a time. See <a class="xref" href="managing_cluster_size#add-an-osd">Section 6.3, “Adding an OSD”</a> for details.
			</p><p>
				When adding/removing Ceph OSD nodes, consider that other ongoing processes will have an impact on performance too. To reduce the impact on client I/O, we recommend the following:
			</p><div class="orderedlist"><ol class="orderedlist" type="1"><li class="listitem">
						<span class="strong strong"><strong>Calculate capacity:</strong></span> Before removing a Ceph OSD node, ensure that the storage cluster can backfill the contents of all its OSDs <span class="strong strong"><strong>WITHOUT</strong></span> reaching the <code class="literal">full ratio</code>. Reaching the <code class="literal">full ratio</code> will cause the cluster to refuse write operations.
					</li><li class="listitem"><p class="simpara">
						<span class="strong strong"><strong>Temporarily Disable Scrubbing</strong></span>: Scrubbing is essential to ensuring the durability of the storage cluster’s data; however, it is resource intensive. Before adding/ removing a Ceph OSD node, disable scrubbing and deep scrubbing and let the current scrubbing operations complete before proceeding, for example:
					</p><pre class="screen"># ceph osd set noscrub
# ceph osd set nodeep-scrub</pre><p class="simpara">
						Once you have added or removed a Ceph OSD node and the storage cluster has returned to an <code class="literal">active+clean</code> state, unset the <code class="literal">noscrub</code> and <code class="literal">nodeep-scrub</code> settings. See <a class="xref" href="overrides#ceph-overrides">Chapter 4, <em>Overrides</em></a> for additional details.
					</p></li><li class="listitem"><p class="simpara">
						<span class="strong strong"><strong>Limit Backfill and Recovery</strong></span>: If you have reasonable data durability, for example, <code class="literal">osd pool default size = 3</code> and <code class="literal">osd pool default min size = 2</code>, there is nothing wrong with operating in a <code class="literal">degraded</code> state. You can tune the Ceph storage cluster for the fastest possible recovery time, but this will impact Ceph client I/O performance significantly. To maintain the highest Ceph client I/O performance, limit the backfill and recovery operations and allow them to take longer, for example:
					</p><pre class="screen">osd_max_backfills = 1
osd_recovery_max_active = 1
osd_recovery_op_priority = 1</pre><p class="simpara">
						You can also set sleep and delay parameters such as <code class="literal">osd_recovery_sleep</code>.
					</p></li></ol></div><p>
				Finally, if you are expanding the size of the storage cluster, you may need to increase the number of placement groups. If you determine that you need to expand the number of placement groups, we recommend making incremental increases in the number of placement groups. Increasing the number of placement groups by a significant number will cause performance to degrade considerably.
			</p></section><section class="section" id="removing_a_node"><div class="titlepage"><div><div><h2 class="title">8.3. Removing a Node</h2></div></div></div><p id="add-remove-osd-nodes-rm-proc">
				Before removing a Ceph OSD node, ensure that your cluster can back-fill the contents of all its OSDs WITHOUT reaching the full ratio. Reaching the full ratio will cause the cluster to refuse write operations.
			</p><div class="orderedlist"><ol class="orderedlist" type="1"><li class="listitem"><p class="simpara">
						Use the following commands to check cluster capacity:
					</p><pre class="screen"># ceph df
# rados df
# ceph osd df</pre></li><li class="listitem"><p class="simpara">
						Temporarily disable scrubbing.
					</p><pre class="screen"># ceph osd set noscrub
# ceph osd set nodeep-scrub</pre></li><li class="listitem"><p class="simpara">
						Limit back-fill and recovery.
					</p><pre class="screen">osd_max_backfills = 1
osd_recovery_max_active = 1
osd_recovery_op_priority = 1</pre><p class="simpara">
						See <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/configuration-guide/chapter-1-configuration-reference#setting_a_specific_configuration_setting_at_runtime">Setting a Specific Configuration Setting at Runtime</a> for details.
					</p></li><li class="listitem"><p class="simpara">
						Remove each Ceph OSD on the node from the Ceph Storage Cluster.
					</p><p class="simpara">
						When removing an OSD node from a Ceph cluster Red Hat recommends removing one OSD at a time within the node and allowing the cluster to recover to an <code class="literal">active+clean</code> state before proceeding to the next OSD.
					</p><p class="simpara">
						See <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/administration-guide/chapter-6-managing-cluster-size#removing_an_osd">Removing an OSD</a> for details on removing an OSD.
					</p><p class="simpara">
						After removing an OSD check to verify the cluster is not nearing the near-full ratio.
					</p><pre class="screen"># ceph -s
# ceph df</pre><p class="simpara">
						Follow this procedure until all OSDs on the node until you have removed all of them from the Ceph Storage cluster.
					</p></li><li class="listitem"><p class="simpara">
						Once all OSDs are removed from the OSD node you can remove the OSD node bucket from the CRUSH map.
					</p><pre class="screen"># ceph osd crush rm {bucket-name}</pre></li><li class="listitem"><p class="simpara">
						Finally, remove the node from Calamari.
					</p><pre class="screen">http://{calamari-fqdn}/api/v2/server/{problematic-host-fqdn}</pre><p class="simpara">
						Click on the 'Delete' button to delete the node from Calamari.
					</p></li></ol></div></section><section class="section" id="adding_a_node"><div class="titlepage"><div><div><h2 class="title">8.4. Adding a Node</h2></div></div></div><p id="add-remove-osd-nodes-add-proc">
				To add an OSD node to a Ceph cluster, first provision the node. See <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/administration-guide/chapter-6-managing-cluster-size#configuring_a_host_2">Configuring a Host</a> for details. Ensure that other nodes in the cluster can reach the new host by its short host name.
			</p><div class="orderedlist"><ol class="orderedlist" type="1"><li class="listitem"><p class="simpara">
						Temporarily disable scrubbing.
					</p><pre class="screen"># ceph osd set noscrub
# ceph osd set nodeep-scrub</pre></li><li class="listitem"><p class="simpara">
						Limit back-fill and recovery.
					</p><pre class="screen">osd_max_backfills = 1
osd_recovery_max_active = 1
osd_recovery_op_priority = 1</pre><p class="simpara">
						See <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/configuration-guide/chapter-1-configuration-reference#setting_a_specific_configuration_setting_at_runtime">Setting a Specific Configuration Setting at Runtime</a> for details.
					</p></li><li class="listitem"><p class="simpara">
						Add the new node to the CRUSH Map.
					</p><pre class="screen"># ceph osd crush add-bucket {bucket-name} {type}</pre><p class="simpara">
						See <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/storage-strategies-guide/chapter-2-crush-administration#add-bucket">Add a Bucket</a> and <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/storage-strategies-guide/chapter-2-crush-administration#move_a_bucket">Move a Bucket</a> for details on placing the node at an appropriate location in the CRUSH hierarchy.
					</p></li><li class="listitem"><p class="simpara">
						Add a Ceph OSD for each storage disk on the node to the Ceph Storage Cluster.
					</p><p class="simpara">
						When adding an OSD node to a Ceph cluster Red Hat recommends adding one OSD at a time within the node and allowing the cluster to recover to an <code class="literal">active+clean</code> state before proceeding to the next OSD.
					</p><p class="simpara">
						See <a class="link" href="https://access.redhat.com/documentation/en/red-hat-ceph-storage/2/paged/administration-guide/chapter-6-managing-cluster-size#adding_an_osd">Adding an OSD</a> for details on adding an OSD.
					</p></li></ol></div></section></section>


  <nav class="book-nav col-sm-11 col-sm-offset-1">
  <ul class="reset clearfix">
    <li class="prev"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/changing_an_osd_drive">Chapter 7. Changing an OSD Drive</a></li>
    <li class="up-toc"></li>
    <li class="next"><a href="/documentation/en-us/red_hat_ceph_storage/2/html/administration_guide/benchmarking_performance">Chapter 9. Benchmarking Performance</a></li>
  </ul>
</nav>


          </div>
              </div>
              <div id="comments-footer" class="book-comments">
          

  

        </div>
          </div>
  </article>
<meta itemscope="" itemref="md1">



    </div>
      <!-- CP_PRIMER_FOOTER -->
            </div>
        </main>
    </div>
    <!--googleoff: all-->
    <div id="to-top"><a class="btn_slideto" href="#masthead" aria-label="Back to Top"><span class="web-icon-upload"></span></a></div>
    <footer class="footer-main">
        <div class="footer-top">
            <div class="container">

              <div class="brand">
                <a href="https://redhat.com">
                  <svg class="rh-logo" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 613 145">
                    <defs>
                      <style>
                        .rh-logo-hat {
                          fill: #e00;
                        }
                        .rh-logo-type {
                          fill: #fff;
                        }
                      </style>
                    </defs>
                    <title>Red Hat</title>
                    <path
                      class="rh-logo-hat"
                      d="M127.47,83.49c12.51,0,30.61-2.58,30.61-17.46a14,14,0,0,0-.31-3.42l-7.45-32.36c-1.72-7.12-3.23-10.35-15.73-16.6C124.89,8.69,103.76.5,97.51.5,91.69.5,90,8,83.06,8c-6.68,0-11.64-5.6-17.89-5.6-6,0-9.91,4.09-12.93,12.5,0,0-8.41,23.72-9.49,27.16A6.43,6.43,0,0,0,42.53,44c0,9.22,36.3,39.45,84.94,39.45M160,72.07c1.73,8.19,1.73,9.05,1.73,10.13,0,14-15.74,21.77-36.43,21.77C78.54,104,37.58,76.6,37.58,58.49a18.45,18.45,0,0,1,1.51-7.33C22.27,52,.5,55,.5,74.22c0,31.48,74.59,70.28,133.65,70.28,45.28,0,56.7-20.48,56.7-36.65,0-12.72-11-27.16-30.83-35.78"/>
                      <path class="rh-logo-band"
                      d="M160,72.07c1.73,8.19,1.73,9.05,1.73,10.13,0,14-15.74,21.77-36.43,21.77C78.54,104,37.58,76.6,37.58,58.49a18.45,18.45,0,0,1,1.51-7.33l3.66-9.06A6.43,6.43,0,0,0,42.53,44c0,9.22,36.3,39.45,84.94,39.45,12.51,0,30.61-2.58,30.61-17.46a14,14,0,0,0-.31-3.42Z"/>
                      <path
                      class="rh-logo-type"
                      d="M579.74,92.8c0,11.89,7.15,17.67,20.19,17.67a52.11,52.11,0,0,0,11.89-1.68V95a24.84,24.84,0,0,1-7.68,1.16c-5.37,0-7.36-1.68-7.36-6.73V68.3h15.56V54.1H596.78v-18l-17,3.68V54.1H568.49V68.3h11.25Zm-53,.32c0-3.68,3.69-5.47,9.26-5.47a43.12,43.12,0,0,1,10.1,1.26v7.15a21.51,21.51,0,0,1-10.63,2.63c-5.46,0-8.73-2.1-8.73-5.57m5.2,17.56c6,0,10.84-1.26,15.36-4.31v3.37h16.82V74.08c0-13.56-9.14-21-24.39-21-8.52,0-16.94,2-26,6.1l6.1,12.52c6.52-2.74,12-4.42,16.83-4.42,7,0,10.62,2.73,10.62,8.31v2.73a49.53,49.53,0,0,0-12.62-1.58c-14.31,0-22.93,6-22.93,16.73,0,9.78,7.78,17.24,20.19,17.24m-92.44-.94h18.09V80.92h30.29v28.82H506V36.12H487.93V64.41H457.64V36.12H439.55ZM370.62,81.87c0-8,6.31-14.1,14.62-14.1A17.22,17.22,0,0,1,397,72.09V91.54A16.36,16.36,0,0,1,385.24,96c-8.2,0-14.62-6.1-14.62-14.09m26.61,27.87h16.83V32.44l-17,3.68V57.05a28.3,28.3,0,0,0-14.2-3.68c-16.19,0-28.92,12.51-28.92,28.5a28.25,28.25,0,0,0,28.4,28.6,25.12,25.12,0,0,0,14.93-4.83ZM320,67c5.36,0,9.88,3.47,11.67,8.83H308.47C310.15,70.3,314.36,67,320,67M291.33,82c0,16.2,13.25,28.82,30.28,28.82,9.36,0,16.2-2.53,23.25-8.42l-11.26-10c-2.63,2.74-6.52,4.21-11.14,4.21a14.39,14.39,0,0,1-13.68-8.83h39.65V83.55c0-17.67-11.88-30.39-28.08-30.39a28.57,28.57,0,0,0-29,28.81M262,51.58c6,0,9.36,3.78,9.36,8.31S268,68.2,262,68.2H244.11V51.58Zm-36,58.16h18.09V82.92h13.77l13.89,26.82H292l-16.2-29.45a22.27,22.27,0,0,0,13.88-20.72c0-13.25-10.41-23.45-26-23.45H226Z"/>
                  </svg>
                </a>
              </div>

            <div role="navigation">
                <h3>Quick Links</h3>
                <ul>
                    <li><a class="download-software" href="https://access.redhat.com/downloads/">Downloads</a></li>
                    <li><a class="manage-subscriptions" href="https://access.redhat.com/management">Subscriptions</a></li>
                    <li><a class="support-cases" href="https://access.redhat.com/support">Support Cases</a></li>
                    <li><a class="customer-service" href="https://access.redhat.com/support/customer-service">Customer Service</a></li>
                    <li><a class="quick-docs" href="https://access.redhat.com/documentation">Product Documentation</a></li>
                </ul>
            </div>

            <div role="navigation">
                <h3>Help</h3>
                <ul>
                    <li><a class="contact-us" href="https://access.redhat.com/support/contact/">Contact Us</a></li>
                    <li><a class="cp-faqs" href="https://access.redhat.com/articles/33844">Customer Portal FAQ</a></li>
                    <li><a class="login-problems" href="https://access.redhat.com/help/login_assistance">Log-in Assistance</a></li>
                </ul>
            </div>

            <div role="navigation">
                <h3>Site Info</h3>
                <ul>
                  <li><a class="trust-red-hat" href="https://www.redhat.com/en/trust">Trust Red Hat</a></li>
                  <li><a class="browser-support-policy" href="https://www.redhat.com/en/about/browser-support">Browser Support Policy</a></li>
                  <li><a class="accessibility" href="https://access.redhat.com/help/accessibility/">Accessibility</a></li>
                  <li><a class="recognition" href="https://access.redhat.com/recognition/">Awards and Recognition</a></li>
                  <li><a class="colophon" href="https://access.redhat.com/help/colophon/">Colophon</a></li>
                </ul>
            </div>

            <div role="navigation">
                <h3>Related Sites</h3>
                <ul>
                    <li><a href="https://www.redhat.com/" class="red-hat-com">redhat.com</a></li>
                    <li><a href="http://developers.redhat.com/" class="red-hat-developers">developers.redhat.com</a></li>
                    <li><a href="https://connect.redhat.com/" class="partner-connect">connect.redhat.com</a></li>
                    <li><a href="https://cloud.redhat.com/" class="cloud-com">cloud.redhat.com</a></li>
                </ul>
            </div>

            <div role="navigation">
                <h3>About</h3>
                <ul>
                    <li><a href="https://access.redhat.com/subscription-value" class="subscription-value">Red Hat Subscription Value</a></li>
                    <li><a href="https://www.redhat.com/about/" class="about-red-hat">About Red Hat</a></li>
                    <li><a href="http://jobs.redhat.com" class="about-jobs">Red Hat Jobs</a></li>
                </ul>
            </div>

            </div>
        </div>

        <div class="anchor">
            <div class="container">
                <div class="status-legal">
                    <a hidden href="https://status.redhat.com" class="status-page-widget">
                          <span class="status-description"></span>
                          <span class="status-dot shape-circle"></span>
                    </a>
                    <div class="legal-copyright">
                        <div class="copyright">Copyright © 2022 Red Hat, Inc.</div>

                        <div role="navigation" class="legal">
                            <ul>
                                <li><a href="http://www.redhat.com/en/about/privacy-policy" class="privacy-policy">Privacy Statement</a></li>
                                <li><a href="https://access.redhat.com/help/terms/" class="terms-of-use">Customer Portal Terms of Use</a></li>
                                <li><a href="http://www.redhat.com/en/about/all-policies-guidelines" class="all-policies">All Policies and Guidelines</a></li>
                                <li><a id="teconsent"></a></li>
                            </ul>
                        </div>
                    </div>
                </div>
                <div class="social">
                    <a href="http://www.redhat.com/summit/" class="summit">
                      <img src="https://access.redhat.com/chrome_themes/nimbus/img/rh-summit-red-a.svg" alt="Red Hat Summit" />
                    </a>

                    <div class="social-media">
                        <a href="https://twitter.com/RedHatSupport" class="sm-icon twitter"><span class="nicon-twitter"></span><span class="offscreen">Twitter</span></a>                        
                    </div>
                </div>
            </div>
        </div>
    </footer>
    <!-- TrustArc -->
    <div id="consent_blackbar"></div> 
    <!--googleon: all-->
</div>
<!-- /CP_PRIMER_FOOTER -->


  </div>

    
  </body>
</html>

```