```
struct Config {
	...
	
	/// Soft limit of #clauses (6MC/GB)
    pub c_cls_lim: usize,

    /// CPU time limit in sec.
    pub c_timeout: f64,

	...
}


default:

	c_cls_lim: 0,
	c_timeout: 5000.0,
```


