# Handling a disk failure
See [redhat](https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure)


--------------------------------------------------------------------------------------------------------------------------------------------


```html
<!DOCTYPE html>
<html lang="en" dir="ltr" prefix="content: http://purl.org/rss/1.0/modules/content/  dc: http://purl.org/dc/terms/  foaf: http://xmlns.com/foaf/0.1/  og: http://ogp.me/ns#  rdfs: http://www.w3.org/2000/01/rdf-schema#  schema: http://schema.org/  sioc: http://rdfs.org/sioc/ns#  sioct: http://rdfs.org/sioc/types#  skos: http://www.w3.org/2004/02/skos/core#  xsd: http://www.w3.org/2001/XMLSchema# ">
  <head>
    <meta charset="utf-8" />
<link rel="canonical" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure" />
<link rel="shortlink" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure" />
<meta property="og:site_name" content="Red Hat Customer Portal" />
<meta property="og:type" content="article" />
<meta property="og:url" content="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure" />
<meta property="og:title" content="Chapter 2. Handling a disk failure Red Hat Ceph Storage 3 | Red Hat Customer Portal" />
<meta property="og:description" content="The Red Hat Customer Portal delivers the knowledge, expertise, and guidance available through your Red Hat subscription." />
<meta property="og:image" content="https://access.redhat.com/webassets/avalon/g/shadowman-200.png" />
<meta name="twitter:card" content="summary" />
<meta name="twitter:description" content="The Red Hat Customer Portal delivers the knowledge, expertise, and guidance available through your Red Hat subscription." />
<meta name="twitter:title" content="Chapter 2. Handling a disk failure Red Hat Ceph Storage 3 | Red Hat Customer Portal" />
<meta name="twitter:url" content="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure" />
<meta name="twitter:image" content="https://access.redhat.com/webassets/avalon/g/shadowman-200.png" />
<meta name="title" content="Chapter 2. Handling a disk failure Red Hat Ceph Storage 3 | Red Hat Customer Portal" />
<meta name="Generator" content="Drupal 9 (https://www.drupal.org)" />
<meta name="MobileOptimized" content="width" />
<meta name="HandheldFriendly" content="true" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<meta name="revision" product="8aa6553b-5ad0-4578-8424-0b30477e29d3" title="f141eda9-4fdd-4904-b4d9-eeb4581ac5f8" page="50120a20-c1f1-4bbb-9fdf-18370c661f4b" revision="f0a1db23c4af46b30d701c7eab995d2ae66ae2f0:en-us" body="073c71eb1a6fa71db1951f88bb3f0034.html" toc="298f312ab166d2d8d84af96f9e31130e.json" />

    <title>Chapter 2. Handling a disk failure Red Hat Ceph Storage 3 | Red Hat Customer Portal</title>
    <link rel="stylesheet" media="all" href="/sites/dxp-docs/files/css/css_iX891cueuzEdQmrffTZ8oV8GqvQlDfIN-93bppCK9lc.css" />

    
    <script type="application/json" data-drupal-selector="drupal-settings-json">{"path":{"baseUrl":"\/","scriptPath":null,"pathPrefix":"","currentPath":"documentation\/en-us\/red_hat_ceph_storage\/3\/html\/operations_guide\/handling-a-disk-failure","currentPathIsAdmin":false,"isFront":false,"currentLanguage":"en"},"pluralDelimiter":"\u0003","suppressDeprecationErrors":true,"red_hat_jwt":{"client_id":"customer-portal","cookie_name":"rh_jwt","leeway":"0","realm":"redhat-external","sso_host":"https:\/\/sso.redhat.com\/"},"user":{"uid":0,"permissionsHash":"d8ea0bce2d740dacbdfe0257cf55baa0e33f7fb8468a26d055ce75daaaa2d315"}}</script>
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
        fetchdate : "2022-04-12T05:15:07-0400",
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
        

                                                                                                        <script>breadcrumbs = [["Products & Services","\/products\/"],["Product Documentation","\/documentation"],["Red Hat Ceph Storage","\/documentation\/en-us\/red_hat_ceph_storage"],["3","\/documentation\/en-us\/red_hat_ceph_storage\/3"],["Operations Guide","\/documentation\/en-us\/red_hat_ceph_storage\/3\/html\/operations_guide"],["Chapter\u00a02.\u00a0Handling a disk failure","\/documentation\/en-us\/red_hat_ceph_storage\/3\/html\/operations_guide\/handling-a-disk-failure"]]</script>

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
              <a href="/documentation/ja-jp/red_hat_ceph_storage/3/html/operations_guide/index">日本語</a>
            </li>
                      <li>
              <a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/index">English</a>
            </li>
                  </ul>
      </div>
      <div class="doc-format btn-group">
        <button type="button" class="btn btn-app dropdown-toggle" data-toggle="dropdown" aria-expanded="false">
          Multi-page HTML <span class="caret"></span>
        </button>
        <ul class="dropdown-menu" role="menu">
                      <li><a href="/documentation/en-us/red_hat_ceph_storage/3/html-single/operations_guide">Single-page HTML</a></li>
                      <li><a href="/documentation/en-us/red_hat_ceph_storage/3/pdf/operations_guide/Red_Hat_Ceph_Storage-3-Operations_Guide-en-US.pdf">PDF</a></li>
                      <li><a href="/documentation/en-us/red_hat_ceph_storage/3/epub/operations_guide/Red_Hat_Ceph_Storage-3-Operations_Guide-en-US.epub">ePub</a></li>
                  </ul>
      </div>
    </div>
          <ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/index">Operations Guide</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size">1. Managing the storage cluster size</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#prerequisites">1.1. Prerequisites</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#ceph-monitors-ops">1.2. Ceph Monitors</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#preparing-a-new-ceph-monitor-node-ops">1.2.1. Preparing a new Ceph Monitor node</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#adding-a-ceph-monitor-using-ansible-ops">1.2.2. Adding a Ceph Monitor using Ansible</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#adding-a-ceph-monitor-using-the-command-line-interface-ops">1.2.3. Adding a Ceph Monitor using the command-line interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#removing-a-ceph-monitor-using-ansible-ops">1.2.4. Removing a Ceph Monitor using Ansible</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#removing-a-ceph-monitor-using-the-command-line-interface-ops">1.2.5. Removing a Ceph Monitor using the command-line interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#removing-a-ceph-monitor-from-an-unhealthy-storage-cluster-ops">1.2.6. Removing a Ceph Monitor from an unhealthy storage cluster</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#ceph-osds-ops">1.3. Ceph OSDs</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#ceph-osd-node-configuration-ops">1.3.1. Ceph OSD node configuration</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#mapping-a-container-osd-id-to-a-drive-ops">1.3.2. Mapping a container OSD ID to a drive</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#adding-a-ceph-osd-using-ansible-with-the-same-disk-topology-ops">1.3.3. Adding a Ceph OSD using Ansible with the same disk topology</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#adding-a-ceph-osd-using-ansible-with-different-disk-topologies-ops">1.3.4. Adding a Ceph OSD using Ansible with different disk topologies</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#adding-a-ceph-osd-using-the-command-line-interface-ops">1.3.5. Adding a Ceph OSD using the command-line interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#removing-a-ceph-osd-using-ansible-ops">1.3.6. Removing a Ceph OSD using Ansible</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#removing-a-ceph-osd-using-the-command-line-interface-ops">1.3.7. Removing a Ceph OSD using the command-line interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#replacing-a-journal-using-the-command-line-interface-ops">1.3.8. Replacing a journal using the command-line interface</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#observing-the-data-migration-ops">1.3.9. Observing the data migration</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#recalculating-the-placement-groups-ops">1.4. Recalculating the placement groups</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#using-the-ceph-manager-balancer-module-ops">1.5. Using the Ceph Manager balancer module</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size#additional_resources">1.6. Additional Resources</a></li></ol></li><li class="leaf active"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure">2. Handling a disk failure</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure#prerequisites_2">2.1. Prerequisites</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure#disk-failures-ops">2.2. Disk failures</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure#replacing-a-failed-osd-disk-ops">2.2.1. Replacing a failed OSD disk</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure#replacing-an-osd-drive-while-retaining-the-osd-id-ops">2.2.2. Replacing an OSD drive while retaining the OSD ID</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-disk-failure#simulating-a-disk-failure-ops">2.3. Simulating a disk failure</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure">3. Handling a node failure</a><ol class="menu"><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#prerequisites_3">3.1. Prerequisites</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#considerations-before-adding-or-removing-a-node-ops">3.2. Considerations before adding or removing a node</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#performance-considerations-ops">3.3. Performance considerations</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#recommendations-for-adding-or-removing-nodes-ops">3.4. Recommendations for adding or removing nodes</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#adding-a-ceph-osd-node-ops">3.5. Adding a Ceph OSD node</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#removing-a-ceph-osd-node-ops">3.6. Removing a Ceph OSD node</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure#simulating-a-node-failure-ops">3.7. Simulating a node failure</a></li></ol></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-data-center-failure-ops">4. Handling a data center failure</a></li><li class="leaf"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/legal-notice">Legal Notice</a></li></ol>
      </div>
</nav>


                          <div class="doc-wrapper">
            

  <div class="card card-light card-md push-bottom">
  <h2 class="card-heading card-heading-red card-heading-sm card-heading-flush">Red Hat Training</h2>
  <p>A Red Hat training course is available for <a href="https://www.redhat.com/en/services/training/ceph125-red-hat-ceph-storage-architecture-and-administration/?intcmp=701f2000001D4RsAAK&amp;" class="cta-link">Red Hat Ceph Storage</a></p>
</div>



  <div class="pane-page-title">
    <h1 class="title" itemprop="name">Chapter 2. Handling a disk failure</h1>
  </div>


  <section class="chapter" id="handling-a-disk-failure"><p>
			As a storage administrator, you will have to deal with a disk failure at some point over the life time of the storage cluster. Testing and simulating a disk failure before a real failure happens will ensure you are ready for when the real thing does happen.
		</p><p>
			Here is the high-level workflow for replacing a failed disk:
		</p><div class="orderedlist"><ol class="orderedlist" type="1"><li class="listitem">
					Find the failed OSD.
				</li><li class="listitem">
					Take OSD out.
				</li><li class="listitem">
					Stop the OSD daemon on the node.
				</li><li class="listitem">
					Check Ceph’s status.
				</li><li class="listitem">
					Remove the OSD from the CRUSH map.
				</li><li class="listitem">
					Delete the OSD authorization.
				</li><li class="listitem">
					Remove the OSD from the storage cluster.
				</li><li class="listitem">
					Unmount the filesystem on node.
				</li><li class="listitem">
					Replace the failed drive.
				</li><li class="listitem">
					Add the OSD back to the storage cluster.
				</li><li class="listitem">
					Check Ceph’s status.
				</li></ol></div><section class="section" id="prerequisites_2"><div class="titlepage"><div><div><h2 class="title">2.1. Prerequisites</h2></div></div></div><div class="itemizedlist"><ul class="itemizedlist" type="disc"><li class="listitem">
						A running Red Hat Ceph Storage cluster.
					</li><li class="listitem">
						A failed disk.
					</li></ul></div></section><section class="section" id="disk-failures-ops"><div class="titlepage"><div><div><h2 class="title">2.2. Disk failures</h2></div></div></div><p>
				Ceph is designed for fault tolerance, which means Ceph can operate in a <code class="literal">degraded</code> state without losing data. Ceph can still operate even if a data storage drive fails. The <code class="literal">degraded</code> state means the extra copies of the data stored on other OSDs will backfill automatically to other OSDs in the storage cluster. When an OSD gets marked <code class="literal">down</code> this can mean the drive has failed.
			</p><p>
				When a drive fails, initially the OSD status will be <code class="literal">down</code>, but still <code class="literal">in</code> the storage cluster. Networking issues can also mark an OSD as <code class="literal">down</code> even if it is really <code class="literal">up</code>. First check for any network issues in the environment. If the networking checks out okay, then it is likely the OSD drive has failed.
			</p><p>
				Modern servers typically deploy with hot-swappable drives allowing you to pull a failed drive and replace it with a new one without bringing down the node. However, with Ceph you will also have to remove the software-defined part of the OSD.
			</p><section class="section" id="replacing-a-failed-osd-disk-ops"><div class="titlepage"><div><div><h3 class="title">2.2.1. Replacing a failed OSD disk</h3></div></div></div><p>
					The general procedure for replacing an OSD involves removing the OSD from the storage cluster, replacing the drive and then recreating the OSD.
				</p><div class="admonition important"><div class="admonition_header">Important</div><div><p>
						When replacing the BlueStore <code class="literal">block.db</code> disk that contains the BlueStore OSD’s database partitions, Red Hat only supports the re-deploying of all OSDs using Ansible. A corrupt <code class="literal">block.db</code> files will impact all OSDs which are included in that <code class="literal">block.db</code> files.
					</p></div></div><div class="itemizedlist"><p class="title"><strong>Prerequisites</strong></p><ul class="itemizedlist" type="disc"><li class="listitem">
							A running Red Hat Ceph Storage cluster.
						</li><li class="listitem">
							A failed disk.
						</li></ul></div><div class="orderedlist"><p class="title"><strong>Procedure</strong></p><ol class="orderedlist" type="1"><li class="listitem"><p class="simpara">
							Check storage cluster health:
						</p><pre class="screen"># ceph health</pre></li><li class="listitem"><p class="simpara">
							Identify the OSD location in the CRUSH hierarchy:
						</p><pre class="screen"># ceph osd tree | grep -i down</pre></li><li class="listitem"><p class="simpara">
							On the OSD node, try to start the OSD:
						</p><pre class="screen"># systemctl start ceph-osd@$OSD_ID</pre><p class="simpara">
							If the command indicates that the OSD is already running, there might be a heartbeat or networking issue. If you cannot restart the OSD, then the drive might have failed.
						</p><div class="admonition note"><div class="admonition_header">Note</div><div><p>
								If the OSD is <code class="literal">down</code>, then the OSD will eventually get marked <code class="literal">out</code>. This is normal behavior for Ceph Storage. When the OSD gets marked <code class="literal">out</code>, other OSDs with copies of the failed OSD’s data will begin backfilling to ensure that the required number of copies exist within the storage cluster. While the storage cluster is backfilling, the cluster will be in a <code class="literal">degraded</code> state.
							</p></div></div></li><li class="listitem"><p class="simpara">
							For containerized deployments of Ceph, try to start the OSD container by referencing the drive associated with the OSD:
						</p><pre class="screen"># systemctl start ceph-osd@$OSD_DRIVE</pre><p class="simpara">
							If the command indicates that the OSD is already running, there might be a heartbeat or networking issue. If you cannot restart the OSD, then the drive might have failed.
						</p><div class="admonition note"><div class="admonition_header">Note</div><div><p>
								The drive associated with the OSD can be determined by <a class="link" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html-single/operations_guide/#mapping-a-container-osd-id-to-a-drive-ops">Mapping a container OSD ID to a drive</a>.
							</p></div></div></li><li class="listitem"><p class="simpara">
							Check the failed OSD’s mount point:
						</p><div class="admonition note"><div class="admonition_header">Note</div><div><p>
								For containerized deployments of Ceph, if the OSD is down the container will be down and the OSD drive will be unmounted, so you cannot run <code class="literal">df</code> to check its mount point. Use another method to determine if the OSD drive has failed. For example, run <code class="literal">smartctl</code> on the drive from the container node.
							</p></div></div><pre class="screen"># df -h</pre><p class="simpara">
							If you cannot restart the OSD, you can check the mount point. If the mount point no longer appears, then you can try remounting the OSD drive and restarting the OSD. If you cannot restore the mount point, then you might have a failed OSD drive.
						</p><p class="simpara">
							Using the <code class="literal">smartctl</code> utility cab help determine if the drive is healthy. For example:
						</p><pre class="screen"># yum install smartmontools
# smartctl -H /dev/$DRIVE</pre><p class="simpara">
							If the drive has failed, you will need to replace it.
						</p></li><li class="listitem"><p class="simpara">
							Stop the OSD process:
						</p><pre class="screen"># systemctl stop ceph-osd@$OSD_ID</pre><div class="orderedlist"><ol class="orderedlist" type="a"><li class="listitem"><p class="simpara">
									If using <span class="strong strong"><strong>FileStore</strong></span>, then flush the journal to disk:
								</p><pre class="screen"># ceph osd -i $$OSD_ID --flush-journal</pre></li></ol></div></li><li class="listitem"><p class="simpara">
							For containerized deployments of Ceph, stop the OSD container by referencing the drive associated with the OSD:
						</p><pre class="screen"># systemctl stop ceph-osd@$OSD_DRIVE</pre></li><li class="listitem"><p class="simpara">
							Remove the OSD out of the storage cluster:
						</p><pre class="screen"># ceph osd out $OSD_ID</pre></li><li class="listitem"><p class="simpara">
							Ensure the failed OSD is backfilling:
						</p><pre class="screen"># ceph -w</pre></li><li class="listitem"><p class="simpara">
							Remove the OSD from the CRUSH Map:
						</p><pre class="screen"># ceph osd crush remove osd.$OSD_ID</pre><div class="admonition note"><div class="admonition_header">Note</div><div><p>
								This step is only needed, if you are permanently removing the OSD and not redeploying it.
							</p></div></div></li><li class="listitem"><p class="simpara">
							Remove the OSD’s authentication keys:
						</p><pre class="screen"># ceph auth del osd.$OSD_ID</pre></li><li class="listitem"><p class="simpara">
							Verify that the keys for the OSD are not listed:
						</p><pre class="screen"># ceph auth list</pre></li><li class="listitem"><p class="simpara">
							Remove the OSD from the storage cluster:
						</p><pre class="screen"># ceph osd rm osd.$OSD_ID</pre></li><li class="listitem"><p class="simpara">
							Unmount the failed drive path:
						</p><div class="admonition note"><div class="admonition_header">Note</div><div><p>
								For containerized deployments of Ceph, if the OSD is down the container will be down and the OSD drive will be unmounted. In this case there is nothing to unmount and this step can be skipped.
							</p></div></div><pre class="screen"># umount /var/lib/ceph/osd/$CLUSTER_NAME-$OSD_ID</pre></li><li class="listitem"><p class="simpara">
							Replace the physical drive. Refer to the hardware vendor’s documentation for the node. If the drive is hot swappable, simply replace the failed drive with a new drive. If the drive is NOT hot swappable and the node contains multiple OSDs, you MIGHT need to bring the node down to replace the physical drive. If you need to bring the node down temporarily, you might set the cluster to <code class="literal">noout</code> to prevent backfilling:
						</p><pre class="screen"># ceph osd set noout</pre><p class="simpara">
							Once you replace the drive and you bring the node and its OSDs back online, remove the <code class="literal">noout</code> setting:
						</p><pre class="screen"># ceph osd unset noout</pre><p class="simpara">
							Allow the new drive to appear under the <code class="literal">/dev/</code> directory and make a note of the drive path before proceeding further.
						</p></li><li class="listitem">
							Find the OSD drive and format the disk.
						</li><li class="listitem"><p class="simpara">
							Recreate the OSD:
						</p><div class="orderedlist"><ol class="orderedlist" type="a"><li class="listitem">
									Using <a class="link" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html-single/operations_guide/index#adding_a_ceph_osd_with_ansible">Ansible</a>.
								</li><li class="listitem">
									Using the <a class="link" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html-single/operations_guide/index#adding_a_ceph_osd_with_the_command_line_interface">command-line interface</a>.
								</li></ol></div></li><li class="listitem"><p class="simpara">
							Check the CRUSH hierarchy to ensure it is accurate:
						</p><pre class="screen"># ceph osd tree</pre><p class="simpara">
							If you are not satisfied with the location of the OSD in the CRUSH hierarchy, you might move it with the <code class="literal">move</code> command:
						</p><pre class="screen"># ceph osd crush move $BUCKET_TO_MOVE $BUCKET_TYPE=$PARENT_BUCKET</pre></li><li class="listitem">
							Verify the OSD is online.
						</li></ol></div></section><section class="section" id="replacing-an-osd-drive-while-retaining-the-osd-id-ops"><div class="titlepage"><div><div><h3 class="title">2.2.2. Replacing an OSD drive while retaining the OSD ID</h3></div></div></div><p>
					When replacing a failed OSD drive, you can keep the original OSD ID and CRUSH map entry.
				</p><div class="admonition note"><div class="admonition_header">Note</div><div><p>
						The <code class="literal">ceph-volume lvm</code> commands defaults to BlueStore for OSDs. To use FileStore OSDs, then use the <code class="literal">--filestore</code>, <code class="literal">--data</code> and <code class="literal">--journal</code> options.
					</p><p>
						See the <a class="link" href="https://access.redhat.com/documentation/en-us/red_hat_ceph_storage/3/html-single/operations_guide/#adding_a_ceph_osd_with_the_command_line_interface">Preparing the OSD Data and Journal Drives</a> section for more details.
					</p></div></div><div class="itemizedlist"><p class="title"><strong>Prerequisites</strong></p><ul class="itemizedlist" type="disc"><li class="listitem">
							A running Red Hat Ceph Storage cluster.
						</li><li class="listitem">
							A failed disk.
						</li></ul></div><div class="orderedlist"><p class="title"><strong>Procedure</strong></p><ol class="orderedlist" type="1"><li class="listitem"><p class="simpara">
							Destroy the OSD:
						</p><pre class="screen">ceph osd destroy $OSD_ID --yes-i-really-mean-it</pre><div class="formalpara"><p class="title"><strong>Example</strong></p><p>
								
<pre class="screen">$ ceph osd destroy 1 --yes-i-really-mean-it</pre>

							</p></div></li><li class="listitem"><p class="simpara">
							Optionally, if the replacement disk was used previously, then you need to <code class="literal">zap</code> the disk:
						</p><pre class="screen">ceph-volume lvm zap $DEVICE</pre><div class="formalpara"><p class="title"><strong>Example</strong></p><p>
								
<pre class="screen">$ ceph-volume lvm zap /dev/sdb</pre>

							</p></div></li><li class="listitem"><p class="simpara">
							Create the new OSD with the existing OSD ID:
						</p><pre class="screen">ceph-volume lvm create --osd-id $OSD_ID --data $DEVICE</pre><div class="formalpara"><p class="title"><strong>Example</strong></p><p>
								
<pre class="screen">$ ceph-volume lvm create --osd-id 1 --data /dev/sdb</pre>

							</p></div></li></ol></div></section></section><section class="section" id="simulating-a-disk-failure-ops"><div class="titlepage"><div><div><h2 class="title">2.3. Simulating a disk failure</h2></div></div></div><p>
				There are two disk failure scenarios: hard and soft. A hard failure means replacing the disk. Soft failure might be an issue with the device driver or some other software component.
			</p><p>
				In the case of a soft failure, replacing the disk might not be needed. If replacing a disk, then steps need to be followed to remove the failed disk and add the replacement disk to Ceph. In order to simulate a soft disk failure the best thing to do is delete the device. Choose a device and delete the device from the system.
			</p><pre class="screen">echo 1 &gt; /sys/block/$DEVICE/device/delete</pre><div class="formalpara"><p class="title"><strong>Example</strong></p><p>
					
<pre class="screen">[root@ceph1 ~]# echo 1 &gt; /sys/block/sdb/device/delete</pre>

				</p></div><p>
				In the Ceph OSD log, on the OSD node, Ceph detected the failure and started the recovery process automatically.
			</p><div class="formalpara"><p class="title"><strong>Example</strong></p><p>
					
<pre class="screen">[root@ceph1 ~]# tail -50 /var/log/ceph/ceph-osd.1.log
2017-02-02 12:15:27.490889 7f3e1fa3d800 -1 ^[[0;31m ** ERROR: unable to open OSD superblock on /var/lib/ceph/osd/ceph-1: (5) Input/output error^[[0m
2017-02-02 12:34:17.777898 7fb7df1e7800  0 set uid:gid to 167:167 (ceph:ceph)
2017-02-02 12:34:17.777933 7fb7df1e7800  0 ceph version 10.2.3-17.el7cp (ca9d57c0b140eb5cea9de7f7133260271e57490e), process ceph-osd, pid 1752
2017-02-02 12:34:17.788885 7fb7df1e7800  0 pidfile_write: ignore empty --pid-file
2017-02-02 12:34:17.870322 7fb7df1e7800  0 filestore(/var/lib/ceph/osd/ceph-1) backend xfs (magic 0x58465342)
2017-02-02 12:34:17.871028 7fb7df1e7800  0 genericfilestorebackend(/var/lib/ceph/osd/ceph-1) detect_features: FIEMAP ioctl is disabled via 'filestore fiemap' config option
2017-02-02 12:34:17.871035 7fb7df1e7800  0 genericfilestorebackend(/var/lib/ceph/osd/ceph-1) detect_features: SEEK_DATA/SEEK_HOLE is disabled via 'filestore seek data hole' config option
2017-02-02 12:34:17.871059 7fb7df1e7800  0 genericfilestorebackend(/var/lib/ceph/osd/ceph-1) detect_features: splice is supported
2017-02-02 12:34:17.897839 7fb7df1e7800  0 genericfilestorebackend(/var/lib/ceph/osd/ceph-1) detect_features: syncfs(2) syscall fully supported (by glibc and kernel)
2017-02-02 12:34:17.897985 7fb7df1e7800  0 xfsfilestorebackend(/var/lib/ceph/osd/ceph-1) detect_feature: extsize is disabled by conf
2017-02-02 12:34:17.921162 7fb7df1e7800  1 leveldb: Recovering log #22
2017-02-02 12:34:17.947335 7fb7df1e7800  1 leveldb: Level-0 table #24: started
2017-02-02 12:34:18.001952 7fb7df1e7800  1 leveldb: Level-0 table #24: 810464 bytes OK
2017-02-02 12:34:18.044554 7fb7df1e7800  1 leveldb: Delete type=0 #22
2017-02-02 12:34:18.045383 7fb7df1e7800  1 leveldb: Delete type=3 #20
2017-02-02 12:34:18.058061 7fb7df1e7800  0 filestore(/var/lib/ceph/osd/ceph-1) mount: enabling WRITEAHEAD journal mode: checkpoint is not enabled
2017-02-02 12:34:18.105482 7fb7df1e7800  1 journal _open /var/lib/ceph/osd/ceph-1/journal fd 18: 1073741824 bytes, block size 4096 bytes, directio = 1, aio = 1
2017-02-02 12:34:18.130293 7fb7df1e7800  1 journal _open /var/lib/ceph/osd/ceph-1/journal fd 18: 1073741824 bytes, block size 4096 bytes, directio = 1, aio = 1
2017-02-02 12:34:18.130992 7fb7df1e7800  1 filestore(/var/lib/ceph/osd/ceph-1) upgrade
2017-02-02 12:34:18.136547 7fb7df1e7800  0 &lt;cls&gt; cls/cephfs/cls_cephfs.cc:202: loading cephfs_size_scan
2017-02-02 12:34:18.142863 7fb7df1e7800  0 &lt;cls&gt; cls/hello/cls_hello.cc:305: loading cls_hello
2017-02-02 12:34:18.255019 7fb7df1e7800  0 osd.1 51 crush map has features 2200130813952, adjusting msgr requires for clients
2017-02-02 12:34:18.255041 7fb7df1e7800  0 osd.1 51 crush map has features 2200130813952 was 8705, adjusting msgr requires for mons
2017-02-02 12:34:18.255048 7fb7df1e7800  0 osd.1 51 crush map has features 2200130813952, adjusting msgr requires for osds
2017-02-02 12:34:18.296256 7fb7df1e7800  0 osd.1 51 load_pgs
2017-02-02 12:34:18.561604 7fb7df1e7800  0 osd.1 51 load_pgs opened 152 pgs
2017-02-02 12:34:18.561648 7fb7df1e7800  0 osd.1 51 using 0 op queue with priority op cut off at 64.
2017-02-02 12:34:18.562603 7fb7df1e7800 -1 osd.1 51 log_to_monitors {default=true}
2017-02-02 12:34:18.650204 7fb7df1e7800  0 osd.1 51 done with init, starting boot process
2017-02-02 12:34:19.274937 7fb7b78ba700  0 -- 192.168.122.83:6801/1752 &gt;&gt; 192.168.122.81:6801/2620 pipe(0x7fb7ec4d1400 sd=127 :6801 s=0 pgs=0 cs=0 l=0 c=0x7fb7ec42e480).accept connect_seq 0 vs existing 0 state connecting</pre>

				</p></div><p>
				Looking at osd disk tree we also see the disk is offline.
			</p><pre class="screen">[root@ceph1 ~]# ceph osd tree
ID WEIGHT  TYPE NAME      UP/DOWN REWEIGHT PRIMARY-AFFINITY
-1 0.28976 root default
-2 0.09659     host ceph3
 1 0.09659         osd.1       down 1.00000          1.00000
-3 0.09659     host ceph1
 2 0.09659         osd.2       up  1.00000          1.00000
-4 0.09659     host ceph2
 0 0.09659         osd.0       up  1.00000          1.00000</pre></section></section>


  <nav class="book-nav col-sm-11 col-sm-offset-1">
  <ul class="reset clearfix">
    <li class="prev"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/managing-the-storage-cluster-size">Chapter 1. Managing the storage cluster size</a></li>
    <li class="up-toc"></li>
    <li class="next"><a href="/documentation/en-us/red_hat_ceph_storage/3/html/operations_guide/handling-a-node-failure">Chapter 3. Handling a node failure</a></li>
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