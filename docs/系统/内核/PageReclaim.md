# Page reclaim

## Overview

Swappable pages
- MAP_ANONYMOUS W/O a file
- Private mapping not written to backing store
- process heap and malloc
- pages for IPC

Page thrashing

Page swapping algorithm
- second chance
- LRU algorithm

Page reclaim of Linux kernel
- Checking memory utilization
  - kswapd: periodic
  - direct reclaim

## Managing swap area

### Data structure

struct swap_info_struct
- struct file (/proc/swaps)
- struct block_device
- struct swap_extent
  - struct list_head
- ...

### Swap area operation

Create: mkswap
Activate: swapon -> sys_swapon
- setup_swap_extents
union swap_header

## The swap cache

Identifying swapped-out pages
- struct swp_entry_t
- pte_to_swp_entry

Structure of the Cache
- struct address_space swapper_space
  - struct address_space_operations swap_aops
    - swap_writepage
    - block_sync_page
  - ...

Add new pages
- add_to_swap
- add_to_swap_cache
- get_swap_page
- __add_to_swap_page_cache

Searching for a page
- lookup_swap_cache

Writing data back
- swap_writepage

## Page reclaim

### Overview

kswapd
- balance_pgdat -> shrink_zone

Direct page reclaim
- try_to_free_pages -> shrink_zone

shrink_zone
- shrink_active/inactive_list
- shrink_page_list
- struct scan_control

### Data structure

struct pagevec
- struct page

LRU Cache

### Determining page activity

PG_referenced
PG_active

## The swap token

grab_swap_token

## Handle swap-page fault

do_swap_page -> read_swap_cache_async -> swapin_readahead

## Initiating memory reclaim

### kswapd

kswapd_init -> kswapd_run -> balance_pgdat

### Event of acute memory shortage

try_to_free_page

## Shrinking other caches

struct shrinker
- shrink

Register and remove
- register_shrinker
- remove_shrinker

Shrinking caches
- shrink_slab
- ...