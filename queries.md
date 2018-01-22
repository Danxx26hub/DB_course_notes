## Log Project ##

<p>the following queries will be used in my log project to answer the following questions.</p>

#question 1#

What are the most popular three articles of all time? Which articles have been accessed the most? Present this information as a sorted list with the most popular article at the top.

# Possible Answer:#

select articles.title, (regexp_split_to_array(path, E'/article/'))[2], count (*) as views from articles join log on articles.slug = (regexp_split_to_array(path, E'/article/'))[2] where path != '/' group by (regexp_split_to_array(path, E'/article/'))[2], articles.title order by views desc limit 3;

# Question 2 #

<p>
Who are the most popular article authors of all time? That is, when you sum up all of the articles each author has written, which authors get the most page views? Present this as a sorted list with the most popular author at the top.</P>

# Possible answer: #


