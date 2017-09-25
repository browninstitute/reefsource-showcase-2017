---
layout: page
title: Process
---

### Designing an interface 

To design the interface for Open Contractors, we started from the ground up, interviewing journalists and activists who worked with this data to figure out what questions they would like answered more easily, and what data they considered most important. 

After spending time talking to practitioners at the Washington Post, the Intercept, The Project on Government Oversight (POGO), The Wall Street Journal and The BBC, we determined that the vast size of the database and the clunky means USAspending provided for downloading were some of the biggest barriers journalists faced when using this data on a deadline.

In essense, they were caught between three equally bad choices. 

1. **The graphical interface:** The GUI provided by USAspending allows for fairly easy searching, but only provides a small subset of data, which is often not enough for deep analysis. When accessing the data through the search portal, you cannot open more than one contract at a time (even if you use different tabs), and downloading the contracts will only provide you with about a tenth of the 220+ columns that are in the raw dataset. Many interesting stories are found in the columns not provided.

2. **The bulk downloader:** Provides CSV files, but the files are often far too large to be easily used in a typical spreadsheet application like Excel. It casts a wide net that needs to then be worked with and sorted afterwards. Therefore, if a journalist is looking for all the contracts provided with a certain parameter for the past 15 years, and does not know or have access to tools like SQL, this can be a very difficult task.

3. **The API:** Provides data in XML format, which is difficult and unwiedly to use, even for more seasoned data folks. Learning how to use and pull data from an API, then using the XML data that results from that query is above the level of most journalists.

Early concept drawings focused on context making, graphic representations of data and sharability of information.

![early sketch](img/early-sketch.png)

But we knew we wouldn't be able to understand how we would actually represent the data without creating the actual application.

So to start prototyping the functionality of our new application, we broke off a small subset of the data and began building a Flask application. Flask is a simple Python framework that would help us quickly mimic the functionality of a more robust application framework without creating technical debt.

The work on that version of the application helped us to refine the information we wanted to show, and determine the priority of information to the viewer.

![later version](img/opencontractors.gif)

The Flask application also allowed us to work on the functionality of the site, the general visual sensibility and the graphs and charts, as the database was being built.

### Designing the database

To work properly, Open Contractors needed to fully take apart and rebuild the federal procurement database. The data as we received it came in the bulk flat CSV format. But to make the data more usable, we needed to turn that into a relational database. That would allow us to more easily map the relationships between companies, agencies, contracts, product or service codes, and any number of parameters contained within the database.

To do this, we downloaded a subset of the data, then began to map out the individual entities contained within the data. For example, there were many columns in the dataset related to the company that received the contract, so we bundled them up to create a separate 'contractor' table, that could be linked to from within each contract that it had received. 

This created a relationship between each contract and the company that received it, so that they were now all related to one individual entity.

![database sketch](img/database.png)

However, this was not an easy process. It's not simple to be able to say one company mentioned in one contract is the same company as one mentioned in another contract. Companies change their names over time, or they change their addresses, so it's difficult to be sure of these connections over time. 

We decided to use the DUNS numbers--names given by the Dun and Bradstreet corporation--to start our entity consolidation. A company is given a DUNS number for every individual location they have. For example, the FedEx across the street from your place of work would have a different DUNS number than the FedEx across town. Large corporations may have hundreds or thousands of locations across the country, and therefore may have just as many DUNS numbers. However the contract data provides a 'parent DUNS' field that can often help link many of these disparate locations.

Companies can also change DUNS numbers when they move, and we have not yet found a solution for this. We have been exploring ways to confirm the entity consistency with outside databases that do this sort of work, like Open Corporates, but haven't yet found a way to do this without a high chance of error.



