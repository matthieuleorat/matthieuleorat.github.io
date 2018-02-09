---
layout: post
title:  "Sulu - Create a minimal template"
date:   2018-02-09 14:00:27 +0100
categories: sulu template
---
## Create a new template

Definition of your template  
Location: app/Resources/template/pages/minimal.xml
```
<?xml version="1.0" ?>
<template xmlns="http://schemas.sulu.io/template/template"
          xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
          xsi:schemaLocation="http://schemas.sulu.io/template/template http://schemas.sulu.io/template/template-1.0.xsd">

    <!--
        Unique identifier of the template

        Mandatory

        Must me identical to file name without extension
    -->
    <key>minimal</key>

    <!--
        Twig file reference

        Mandatory

        Sulu automatically adds the .<format>.twig suffix to the view string, depending on the format requested by the client (HTML, JSON, XML, ...).
        Instead of the folder notation with the / you can use the Symfony’s naming convention without the file extension for Twig templates.
    -->
    <view>templates/tour</view>

    <meta>
        <!--
            Template displayed name

            Mandatory
        -->
        <title lang="en">Minimal</title>
    </meta>

    <!--
        Mandatory
    -->
    <controller>SuluWebsiteBundle:Default:index</controller>

    <properties>
        <!-- This section with properties title and url is mandatory -->
        <section name="highlight">
            <properties>
                <property name="title" type="text_line" mandatory="true">
                    <meta>
                        <title lang="en">Title</title>
                        <title lang="de">Titel</title>
                    </meta>
                    <params>
                        <param name="headline" value="true"/>
                    </params>

                    <tag name="sulu.rlp.part"/>
                </property>

                <property name="url" type="resource_locator" mandatory="true">
                    <meta>
                        <title lang="en">Resourcelocator</title>
                        <title lang="de">Adresse</title>
                    </meta>

                    <tag name="sulu.rlp"/>
                </property>
            </properties>
        </section>
    </properties>
</template>
```

### Create your template twig file
Location:  app/Resources/views/templates/minimal.html.twig