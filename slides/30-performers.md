---
author: Display Lab
title: Bitstomach
date: 2019-12-20
---

# Update Performers 
Add information about performers to the spek.

##
```json
"Performers": [
```

<span class="fragment"> 
Performer...
  <pre><code>
  { "@id": "Alice"
  </code></pre>
</span>

<span class="fragment"> 
...deduction about them...
<pre><code>
    "Has Disposition":[
      { "@type": "Postive Performance Gap",
</code></pre>
</span>

<span class="fragment"> 
...for a particular measure
<pre><code>
        "Regarding Measure": "Documentation Rate"}
</code></pre>
</span>

##

```json
"Performers": [
  { "@id": "Alice"
    "Has Disposition": [
      { "@type": "Postive Performance Gap",
        "Regarding Measure": "Documentation Rate"},
      { "@type": "Postive Performance Gap",
        "Regarding Measure": "Documentation Rate"}] }
  { "@id": "Bob"
    ...
```

