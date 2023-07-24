# 0x00-pagination

## Description
The folder contains types of pagination with a csv file available. 

Markup : [0. Simple helper function](./0-simple_helper_function.py) 
Function named index_range that takes two integer arguments page and page_size. The function returns a tuple of size two containing a start index and an end index corresponding to the range of indexes to return in a list for those particular pagination parameters. Page numbers are 1-indexed, i.e. the first page is page 1.

Markup : [1. Simple pagination](./0-simple_helper_function.py)
The function implements a method named "get_page" that takes two integer arguments "page with default value 1" and "page_size with default value 10."
One has to use the CSV file [Popular_Baby_Names](Popular_Baby_Names.csv)
Uses assert to verify that both arguments are integers greater than 0.
Uses index_range to find the correct indexes to paginate the dataset correctly and return the appropriate page of the dataset (i.e. the correct list of rows).
If the input arguments are out of range for the dataset, an empty list should be returned.

: [2. Hypermedia pagination](./2-hypermedia_pagination.py)
Implement a get_hyper method that takes the same arguments (and defaults) as get_page and returns a dictionary containing the following key-value pairs:
    1. page_size: the length of the returned dataset page
    2. page: the current page number
    3. data: the dataset page (equivalent to return from previous task)
    4. next_page: number of the next page, None if no next page
    5. prev_page: number of the previous page, None if no previous page
    6. total_pages: the total number of pages in the dataset as an integer

: [3. Deletion-resilient hypermedia pagination](./3-hypermedia_del_pagination.py)
Implements a get_hyper_index method with two integer arguments: index with a None default value and page_size with default value of 10.
The method should return a dictionary with the following key-value pairs:
        index: the current start index of the return page. That is the index of the first item in the current page. For example if requesting page 3 with page_size 20, and no data was removed from the dataset, the current index should be 60.
        next_index: the next index to query with. That should be the index of the first item after the last item on the current page.
        page_size: the current page size
        data: the actual page of the dataset
__Requirements/Behavior:__
    Use assert to verify that index is in a valid range.
    If the user queries index 0, page_size 10, they will get rows indexed 0 to 9 included.
    If they request the next index (10) with page_size 10, but rows 3, 6 and 7 were deleted, the user should still receive rows indexed 10 to 19 included.