
# Description
Learning the different caching algorithms 

## Files 
* [BaseCaching](base_caching.py "BaseCaching")
The original file that is to be used with this project. 

* [0.Basic dictionary](0-basic_cache.py "0.Basic dictionary")
it Creates a class BasicCache that inherits from BaseCaching and is a caching system:

        * use self.cache_data - dictionary from the parent class BaseCaching
        * This caching system doesn’t have limit
        * def put(self, key, item):
        * Must assign to the dictionary self.cache_data the item value for the key key.
        * If key or item is None, this method should not do anything.
        * def get(self, key):
        * Must return the value in self.cache_data linked to key.
        * If key is None or if the key doesn’t exist in self.cache_data, return None.

* [FIFO Caching](1-fifo_cache.py "FIFO Caching")
Creates a class FIFOCache that inherits from BaseCaching and is a caching system:

* must use self.cache_data - dictionary from the parent class BaseCaching
* You can overload def __init__(self): but don’t forget to call the parent init: super().__init__()
* def put(self, key, item):
* Must assign to the dictionary self.cache_data the item value for the key key.
* If key or item is None, this method should not do anything.
* If the number of items in self.cache_data is higher that BaseCaching.MAX_ITEMS:
* must discard the first item put in cache (FIFO algorithm)
* must print DISCARD: with the key discarded and following by a new line
* def get(self, key):
* Must return the value in self.cache_data linked to key.
* If key is None or if the key doesn’t exist in self.cache_data, return None.

* [LIFO Caching](2-lifo_cache.py "LIFO Caching")
Creates a class LIFOCache that inherits from BaseCaching and is a caching system:

* You must use self.cache_data - dictionary from the parent class BaseCaching

* [LRU Caching](./3-lru_cache.py "LRU Caching")
Creates a class LRUCache that inherits from BaseCaching and is a caching system

* [MRU Caching](./4-mru_cache.py "MRU Caching")
Creates a class MRUCache that inherits from BaseCaching and is a caching system