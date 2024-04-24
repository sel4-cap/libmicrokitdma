# Initialisation of the dma library
## Declare and initialise the dma manager 

```c
static ps_dma_man_t dma_manager;
microkit_dma_manager(&dma_manager);
```
## Initialise the dma
```
/* Add memory to the dma allocator. Pass in the pool to allocate from, the size of this
 * pool in bytes, the page size of the associated mappings and the caching.
 */
int microkit_dma_init(
    void *dma_pool,
    size_t dma_pool_sz,
    size_t page_size,
    bool cached)
```
Calls can now be made into the dma interface, for example to allocate a block of memory:
```c
void* vaddr = dma_manager->dma_alloc_fn(
    size,
    align,
    true,
    PS_MEM_NORMAL);
```
