In real life scenario, if you get your hands on a company's custom recovery image,
You can extract the filesystem.squashfs with all permisions, then decrypt the passwords or search for dirt left by the sysadmin...,
In our case, we found zaz password in .bash_history of root user; what the root user was typing when he was customising the image.
<img src="../img/squ_1.png" width="60%" height=60%>

Extrating filesystem.squashfs.

<img src="../img/squ_2.png" width="60%" height=60%>

Explore root folder.

<img src="../img/squ_3.png" width="60%" height=60%>

cat .bash_history

<img src="../img/squ_4.png" width="60%" height=60%>
