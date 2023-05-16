# 0x01. Caching

# Background Context
In this project, you learn different caching algorithms.

# Resources
Read or watch:

- [Cache replacement policies - FIFO](https://intranet.alxswe.com/rltoken/fjhr6EvFeF3mWwsPQXUKdQ)
- [Cache replacement policies - LIFO](https://intranet.alxswe.com/rltoken/U44RQjXp8xBtsbNIyhHIyw)
- [Cache replacement policies - LRU](https://intranet.alxswe.com/rltoken/gKerxvR4dnXQYkBX2ujZiQ)
- [Cache replacement policies - MRU](https://intranet.alxswe.com/rltoken/Tmk4qEBZ7QTknvbpKabWfQ)
- [Cache replacement policies - LFU](https://intranet.alxswe.com/rltoken/8PEJ8L34bxhL2y--BW5zGQ)

# Learning Objectives
At the end of this project, you are expected to be able to explain to anyone, without the help of Google:

# General
- What a caching system is
- What FIFO means
- What LIFO means
- What LRU means
- What MRU means
- What LFU means
- What the purpose of a caching system
- What limits a caching system have

# More Info
Parent class BaseCaching
All your classes must inherit from BaseCaching defined below:

$ cat base_caching.py
#!/usr/bin/python3
""" BaseCaching module
"""

class BaseCaching():
    """ BaseCaching defines:
      - constants of your caching system
      - where your data are stored (in a dictionary)
    """
    MAX_ITEMS = 4

    def __init__(self):
        """ Initiliaze
        """
        self.cache_data = {}

    def print_cache(self):
        """ Print the cache
        """
        print("Current cache:")
        for key in sorted(self.cache_data.keys()):
            print("{}: {}".format(key, self.cache_data.get(key)))

    def put(self, key, item):
        """ Add an item in the cache
        """
        raise NotImplementedError("put must be implemented in your cache class")

    def get(self, key):
        """ Get an item by key
        """
        raise NotImplementedError("get must be implemented in your cache class")

# Tasks
# 0. Basic dictionary
- Create a class BasicCache that inherits from BaseCaching and is a caching system:

- You must use self.cache_data - dictionary from the parent class BaseCaching
- This caching system doesn’t have limit
def put(self, key, item):
- Must assign to the dictionary self.cache_data the item value for the key key.
- If key or item is None, this method should not do anything.
def get(self, key):
- Must return the value in self.cache_data linked to key.
- If key is None or if the key doesn’t exist in self.cache_data, return None.

# 1. FIFO caching
- Create a class FIFOCache that inherits from BaseCaching and is a caching system:

- You must use self.cache_data - dictionary from the parent class BaseCaching
- You can overload def __init__(self): but don’t forget to call the parent init: super().__init__()
def put(self, key, item):
- Must assign to the dictionary self.cache_data the item value for the key key.
- If key or item is None, this method should not do anything.
- If the number of items in self.cache_data is higher that BaseCaching.MAX_ITEMS:
- you must discard the first item put in cache (FIFO algorithm)
- you must print DISCARD: with the key discarded and following by a new line
def get(self, key):
- Must return the value in self.cache_data linked to key.
- If key is None or if the key doesn’t exist in self.cache_data, return None.

# 2. LIFO Caching
- Create a class LIFOCache that inherits from BaseCaching and is a caching system:

- You must use self.cache_data - dictionary from the parent class BaseCaching
- You can overload def __init__(self): but don’t forget to call the parent init: super().__init__()
def put(self, key, item):
- Must assign to the dictionary self.cache_data the item value for the key key.
- If key or item is None, this method should not do anything.
- If the number of items in self.cache_data is higher that BaseCaching.MAX_ITEMS:
- you must discard the last item put in cache (LIFO algorithm)
- you must print DISCARD: with the key discarded and following by a new line
def get(self, key):
- Must return the value in self.cache_data linked to key.
- If key is None or if the key doesn’t exist in self.cache_data, return None.

# 3. LRU Caching
- Create a class LRUCache that inherits from BaseCaching and is a caching system:

- You must use self.cache_data - dictionary from the parent class BaseCaching
- You can overload def __init__(self): but don’t forget to call the parent init: super().__init__()
 def put(self, key, item):
- Must assign to the dictionary self.cache_data the item value for the key key.
- If key or item is None, this method should not do anything.
- If the number of items in self.cache_data is higher that BaseCaching.MAX_ITEMS:
- you must discard the least recently used item (LRU algorithm)
- you must print DISCARD: with the key discarded and following by a new line
def get(self, key):
- Must return the value in self.cache_data linked to key.
- If key is None or if the key doesn’t exist in self.cache_data, return None.

# 4. MRU Caching
- Create a class MRUCache that inherits from BaseCaching and is a caching system:

-You must use self.cache_data - dictionary from the parent class BaseCaching
-You can overload def __init__(self): but don’t forget to call the parent init: super().__init__()
def put(self, key, item):
- Must assign to the dictionary self.cache_data the item value for the key key.
- If key or item is None, this method should not do anything.
- If the number of items in self.cache_data is higher that BaseCaching.MAX_ITEMS:
- you must discard the most recently used item (MRU algorithm)
- you must print DISCARD: with the key discarded and following by a new line
def get(self, key):
- Must return the value in self.cache_data linked to key.
- If key is None or if the key doesn’t exist in self.cache_data, return None.


# AUTHOR
- [Simanga Mchunu](https://twitter.com/Simacoder)
