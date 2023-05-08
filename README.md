Download Link: https://assignmentchef.com/product/solved-si-507-homework-7-web-scraping-crawling
<br>
<strong>Homework Objectives</strong>

<ul>

 <li>Become competent with website structure and crawling multiple pages</li>

 <li>Understanding user agent concept and how to utilize it in the request</li>

</ul>




<strong>Supporting Material</strong>

<ul>

 <li>Beautifulsoup Documentation<a href="https://www.crummy.com/software/BeautifulSoup/bs4/doc">https://www.crummy.com/software/BeautifulSoup/bs4/doc</a></li>

 <li>Initial page of the UMSI directory website<a href="https://www.si.umich.edu/directory?field_person_firstname_value=&amp;field_person_lastname_value=&amp;rid=All">https://www.si.umich.edu/directory?field_person_firstname_value=&amp;field_person_lastname_value=&amp;rid=All</a></li>

 <li>Additional pages of the directory are sequentially numbered through the “page” paramter in the URL. The second page in the directory is:<a href="https://www.si.umich.edu/directory?field_person_firstname_value=&amp;field_person_lastname_value=&amp;rid=All&amp;page=1">https://www.si.umich.edu/directory?field_person_firstname_value=&amp;field_person_lastname_value=&amp;rid=All&amp;page=1</a>Third page has “page=2” as the last parameter, and so on.</li>

</ul>

<strong>Starter Files</strong>

We have provided you with the following files:

<ul>

 <li><a href="https://www.dropbox.com/s/1xfsshj7y4lcb0y/hw7_part1.py?dl=0">py</a></li>

 <li><a href="https://www.dropbox.com/s/5izqythuik6a3ic/hw7_part2.py?dl=0">py</a></li>

</ul>




Please use these python files as a template to add your code. You can chose to use additional functions or not, depending on how you would like to structure your code.

<strong> </strong>

<strong>Homework task in brief:</strong>

Your job in this homework is to crawl the UMSI directory website and extract some basic information about each person in the directory. You will then use this information to find out the number of current UMSI PhD students.




<strong>Part 1 (15 points): Crawling the UMSI member (faculty, phD, staff) website with cache</strong>




Write a function called get_umsi_data. The function should access each page of the directory, get the HTML associated with it, and extract data from it. The extracted data should be used to create a dictionary named umsi_people. The keys of this dictionary should be email addresses of each person in the UMSI directory, and the value for each key should be a dictionary containing the person’s name and title.




Your dictionary should end up looking something like this (with a lot more entries, obviously!):

{

“<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="1d70787c7f7f7c79745d6870747e7533787968">[email protected]</a>”: {“name”: Mohamed Abbadi”, “title”: “PhD student”},

“<a href="/cdn-cgi/l/email-protection" class="__cf_email__" data-cfemail="1570747174675560787c767d3b707160">[email protected]</a>”: {“name”: “Eytan Adar”, “title”: “Associate Professor of Electrical Engineering and Computer Science, College of Engineering and Associate Professor of Information, School of Information”}

}




Then write out the dictionary to a file directory_dict.json.







Note:

<ul>

 <li>To get data from the UMSI site, you must have the user-agent headers parameter in your request, so that you will not get blocked by the site. You should use the following user-agent, which has been set up by our system administrators to allow crawling: get(&lt;url you want&gt;, headers={‘User-Agent’: ‘SI_CLASS’})</li>

 <li><strong>Please crawl one single page first and make sure that your code works before crawling the rest of the pages</strong></li>

 <li><strong>Please implement caching </strong>to prevent overwhelming crawling of the UMSI website. (The overwhelming crawling might shut down the website and then you cannot check the crawling program.<strong> The deadline will not be extended because of the shut down problem.</strong> Please see every query as a critical one.)</li>

 <li>Start as early as possible to prevent the above situation.</li>

 <li>The directory_dict.json is not the cache! As always, your cache should use URLs as keys and the html content of the whole web page as the value for each key</li>

</ul>




Sample Command:

$ python3 hw7_part1.py




The output of this command should be a newly created directory_dict.json file.




<strong> </strong>

<strong>Part 2 (5 points): Analyze the data from part 1</strong>




Using the directory_dict.json you generated in part 1, this program should search the data you crawled to find the number of PhD students in the directory.




Sample Command:

$ python3 hw7_part2.py




Sample output:

The number of PhD students: 123




Note:

The number in the sample output is not correct. Your program should return the correct number. (:




<strong> </strong>

<strong>Extra Credit 1 (2 points) Crawling headlines, authors, and time from Detroit Free Press</strong>




Get the headlines, authors and times from the “Trending” section (top right) of the news page in  Detroit Free Press (<a href="https://www.freep.com/news/">https://www.freep.com/news/</a>):










Create a json file called freep.json that contains a list of dictionaries, each dictionary containing the article’s headline, authors/byline, and publication time.







Sample Command:

$ python3 hw7_ec1.py




Sample content of the output json file:

[{“title”: “Sign up for new DTW program, and you won’t need a ticket to pass security at Detroit Metro”, “byline”: “Eric D. Lawrence”, “publication time”: “1:08 p.m. ET Oct. 21, 2019”},

{“title”: “Bedbugs found at Mott Community College’s Flint campus”, “byline”: “Associated Press”, “publication_time”: “1:45 p.m. ET Oct. 21, 2019”}]

(with more entries, obviously)




Notes:

<ul>

 <li>The publication time is provided as a string that is a little more complicated than just the date and time as shown above. It usually has the following form “ Published 1:08 p.m. ET Oct. 21, 2019  |  “ with both leading and trailing spaces, and the pipe symbol after the date. So, you’ll need to clean this up a bit before saving it.</li>

 <li>If the article is brand new, the time may only say “ Published 58 minutes ago” or something like that. It’s ok to save this as the content of your publication_time key.</li>

 <li>The html of the page is messy, so it will take some hunting to get the data you need, but this is how most real website are. Unfortunately.</li>

</ul>










<strong>What to turn in on Canvas</strong>

<ul>

 <li>py</li>

 <li>py</li>

 <li>Any additional extra credit files</li>

</ul>




<strong> </strong>


