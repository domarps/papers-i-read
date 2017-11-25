## Composition Aware Search

Having just read, Spatial-Semantic Search ([notes](https://github.com/domarps/papers-i-read/blob/master/spatial_search.md)), it is easy to see that the paper draws a lot of inspiration from Region-Based Image Retrieval (RIBR) papers. It is a bit concern that the paper does not outline evaluation methodologies on datasets such Visual Genome and MS-COCO or mention about user studies to understand model effectiveness. Such benchmarks are important tools for measuring performance, but in a rapidly evolving field like RIBR it can be difficult to keep up with the state of the art.

Also, it is important to understand how storage mechansims other than IVFADC can enable the maintenance of large index as well as enable fast retrieval of images.

> Our index is likely where the bulk of future work will be valuable. Currently, it requires
about 720 GiB of storage space to serve our entire collection of 120 million images, which is still
large. 

> Specifically, we might see large gains using the inverted multi-index to find candidate images, and using product quantization to heavily compress the stored vectors.



