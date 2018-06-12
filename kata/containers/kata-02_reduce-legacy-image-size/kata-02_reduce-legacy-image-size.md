# Kata-02: Reduce a leagcy image size

This kata wanted train you to reduce the size of a big leagcy image.
The existing IT-world dominated of bad software designes and __solutions__. But it is time to
change it. How you can split your legacy apps into smaller pieces? Reduce size and dependcies

Start small and dirty, but then add quality.

* Choose a heavy loaded container image
  * PHP app with http server and fpm included
  * Java image based on Centos with oracle java
  * node js app with all developer tools shiped.
* Really all things needed?
* Can you split the services or tools into separated images?
* Which tools really needed?
* Is something very bad?
* Drop your unused dependencies
* Discuss container vs. virtuelle machines

Don`t repeat you self!

## Other nice questions

* How you can share binaries, without rebuilding?
* How you redesign and refactor the image productive, with out destroy something?
* Is the developer and production images really the same?
* Which information you needed in a self healing system like kubernetes?

## Helpful informations

* https://hackernoon.com/tips-to-reduce-docker-image-sizes-876095da3b34
* https://blog.codeship.com/reduce-docker-image-size/
* https://docs.docker.com/develop/develop-images/multistage-build/
