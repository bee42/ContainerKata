# Kata-02: Reduce a leagcy image size

This kata wants to train you in reducing the size of a big legacy image.
The existing IT-world is dominated by bad software designs and __solutions__. But it is time to
change it. How you can split your legacy apps into smaller pieces, reducing size and dependencies?

Start small and dirty, but add quality afterwards.

* Choose a heavy loaded container image
  * PHP app with http server and fpm included
  * Java image based on Centos with oracle java
  * node js app with all developer tools shiped.
  * Big Java application image including a RDMS process in the same container
* Are all things really needed?
* Can you split the services or tools into separate images?
* Which tools are really needed?
* Is something very bad?
* Drop your unused dependencies
* Discuss container vs. virtual machines

Don`t repeat you self (DRY)!

## Other nice questions

* How can you share binaries without rebuilding?
* How can you redesign and refactor the image productively, with out destroy something?
* Are the developer and production images really the same?
* Which information is needed in a self healing system like kubernetes?

## Helpful informations

* https://hackernoon.com/tips-to-reduce-docker-image-sizes-876095da3b34
* https://blog.codeship.com/reduce-docker-image-size/
* https://docs.docker.com/develop/develop-images/multistage-build/
