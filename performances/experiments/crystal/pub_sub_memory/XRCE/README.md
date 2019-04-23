### Micro XRCE DDS

Preliminary results using MicroROS: https://micro-ros.github.io/

* **Installation:** at the time of testing, only the `develop` branch supported ROS2 Crystal. You'd need to follow the instructions at [the wiki](https://github.com/micro-ROS/micro-ROS-doc/blob/develop/Installation/Linux_WSBuild%26Install.md), but in step 2 ("**Import Micro-ROS packages**") - instead of getting the .repos files from `master`, get them from `develop`. 
  * Running experiments: the easiest way is to clone this repository into `microros/client_ws/src` and build everything (microROS & performance_test) together.
* **Note:** at the moment, this performance framework does not measure the resources consumed by the uROS agent, so this is not the whole picture. We'll need to make some adjustments and rerun the experiment if we want to compare apples to apples.
#### only_subs, 4mb, FastRTPS vs. Micro-XRCE-DDS
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
