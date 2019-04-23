### Micro XRCE DDS

Preliminary results using MicroROS: https://micro-ros.github.io/
* Note: at the moment this framework does not measure the resources consumed by the uROS agent, so this is not the whole picture. I anticipate the overall resources would still be significantly lower but we'll need to make some adjustments and rerun the experiment.
#### only_subs, 4mb
```
source env.sh
export MAX_PUBLISHERS=1
export MAX_SUBSCRIBERS=1
export MSG_TYPES="4mb"
export DURATION=10
export NUM_EXPERIMENTS=5
bash scripts/only_subs.sh
```

![Plot](4m_subs_vsz.png)
![Plot](4m_subs_rss.png)