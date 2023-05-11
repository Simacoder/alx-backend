# 0x00. Pagination

# Concepts
For this project, we expect you to look at this concept:

- [Back-end concepts](https://intranet.alxswe.com/concepts/557)

# Resources
Read or watch:

- [REST API Design: Pagination](https://intranet.alxswe.com/rltoken/7Kdzi9CH1LdSfNQ4RaJUQw)
- [HATEOAS](https://intranet.alxswe.com/rltoken/tfzcEbTSdMYSYxsspJH_oA)

# Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

- How to paginate a dataset with simple page and page_size parameters
- How to paginate a dataset with hypermedia metadata
- How to paginate in a deletion-resilient manner

# Setup: Popular_Baby_Names.csv
- use this data file for your project
# Tasks
# 0. Simple helper function
- Write a function named index_range that takes two integer arguments page and page_size.

- The function should return a tuple of size two containing a start index and an end index corresponding to the range of indexes to return in a list for those particular pagination parameters.

- Page numbers are 1-indexed, i.e. the first page is page 1.
# 1. Simple pagination
- Copy index_range from the previous task and the following class into your code
- Implement a method named get_page that takes two integer arguments page with default value 1 and page_size with default value 10.
# 2. Hypermedia pagination
- Replicate code from the previous task.

Implement a get_hyper method that takes the same arguments (and defaults) as get_page and returns a dictionary containing the following key-value pairs:

- page_size: the length of the returned dataset page
- page: the current page number
- data: the dataset page (equivalent to return from previous task)
- next_page: number of the next page, None if no next page
- prev_page: number of the previous page, None if no previous page
- total_pages: the total number of pages in the dataset as an integer
# 3. Deletion-resilient hypermedia pagination
- The goal here is that if between two queries, certain rows are removed from the dataset, the user does not miss items from dataset when changing page.

- Start 3-hypermedia_del_pagination.py with this code:

# AUTHOR
- [Simanga Mchunu](https://twitter.com/Simacoder)
