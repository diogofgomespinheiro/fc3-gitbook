# Performance

## <mark style="color:purple;">Units of performance measure:</mark> <a href="#units-of-performance-measure" id="units-of-performance-measure"></a>

* Latency or “response time”
* Throughput

## <mark style="color:purple;">Main reasons for low performance</mark> <a href="#main-reasons-for-low-performance" id="main-reasons-for-low-performance"></a>

* Insufficient processing
* Limited computational resources
* Work in a blocking way
* Synchronous access to resources

## <mark style="color:purple;">How to improve performance:</mark> <a href="#how-to-improve-performance" id="how-to-improve-performance"></a>

* Decrease latency
  * Usually measured in ms
  * It is affected by the time of application processing, network and external requests
* Increase throughput
  * Increase capacity of RPM (requests per minute)
  * Directly linked to latency
* Increase computational capacity (CPU, Disk, Memory, Network)
* Improve software (Algorithms, queries, framework overhead)
* Concurrency and parallelism
* Database (change type, schemas, indexes, etc..)
* Caching

## <mark style="color:purple;">Horizontal vs Vertical scaling</mark> <a href="#horizontal-vs-vertical-scaling" id="horizontal-vs-vertical-scaling"></a>

<figure><img src="../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

## <mark style="color:purple;">Caching</mark> <a href="#caching" id="caching"></a>

* Edge computing
* Static data
* Web pages
* Internal functions
  * Avoids reprocessing of heavy algorithms
  * Access to the database
* Objects

### <mark style="color:green;">Caching: Exclusive vs Shared</mark> <a href="#caching-exclusive-vs-shared" id="caching-exclusive-vs-shared"></a>

#### <mark style="color:yellow;">Exclusive</mark> <a href="#exclusive" id="exclusive"></a>

* Low latency
* Duplicated between nodes
* Session related problems

#### <mark style="color:yellow;">Shared</mark> <a href="#shared" id="shared"></a>

* Higher latency
* There is no duplicated data between nodes
* Shared sessions
* External database
  * MySQL
  * Redis
  * Memcached

### <mark style="color:green;">Caching: Edge Computing</mark> <a href="#caching-edge-computing" id="caching-edge-computing"></a>

* Cache more close to the end user
* Avoids requests to the cloud provider/infra
* Usually for static assets
* CDN
* Cloudflare workers
* Vercel
* Akamai
