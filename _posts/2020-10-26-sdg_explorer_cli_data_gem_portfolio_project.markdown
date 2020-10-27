---
layout: post
title:      "SDG Explorer (CLI Data Gem Portfolio Project)"
date:       2020-10-26 23:22:09 -0400
permalink:  sdg_explorer_cli_data_gem_portfolio_project
---


I created a gem that retrieves and displays annual progress reports for the UN's sustainable development goals. It gathers the information from the UN's SDG website and should automatically include any annual progress reports that are added in the future.

The main hangup I had in working on this project was shifting from the lesson/coding based progress in the course to the planning/thinking process of the project. I knew I wanted to make something that I was interested in, and at first I was thinking of making a project based on a job board that I follow - but that job board ended up not being very accessible (too much javascript) so I switched my plan to the UN SDG Explorer. After a few weeks of mulling over what was possible, I finally sat down and started working through the project in earnest. Once I built out my user story and diagram, I was eager to see it in action.

I set up a few different classes in the app: CLI, Scraper, SDG, and Report.
* The CLI class is responsible for all interaction with the user
* The Scraper class is responsible for collecting information from the UN's website
* The SDG class is responsible for creating and knowing about the different SDGs (each instance of the SDG class represents one of the Goals)
* The Report class is responsible for creating and knowing about the annual progress reports. Each SDG can have many Reports, and each Report belongs to one SDG.

I used Nokogiri to pull the data I wanted from the websites and use it to create new SDGs or add Reports to existing SDGs, scraping each page only when needed and then not again if the data is called for by the user. I built out the CLI to allow users to navigate to any SDG and any available Annual Report until the user chooses to exit the program.

Here's a [short demo video](https://youtu.be/qmJ88fZL25g)!
