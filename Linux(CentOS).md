## Linux 基础:
	 1.挂载-->给分区分配盘符的过程.
	 2.挂载点-->分配的盘符.
	 3.空的目录名称作为挂载点.(理论上任何的空目录都可以作为挂载点,实际有些目录不建议)

		****必须分区****
				
				/		(根分区)
		 	swap分区		(交换分区,内存的2倍,不超过2GB)

		****推荐分区****

				/boot	(启动分区,200MB)


	4.分区配置:
		
		sda1		200		/boot	ext4 
		sda2		2000	/home	ext4
		sda3		1000			swap
		
		sda4		17279			Extend Partition
		  sda5		17278	/		ext4

	5.挂载光盘:

		mkdir /mnt/iso_xp

		mount -t iso9660 /dev/sr0 /mnt/iso_xp

		ls -al /mnt/iso_xp

		umount /mnt/iso_xp

	6.添加用户

		useradd yuri
		passwd	yuri	jsd

	7.查询当前Linux系统登录信息

		$ who
	    用户名	终端		日期			时间		IP地址
		root	tty1	2017-12-12	18:30
		root	pts/0	2017-12-12	18:30	(192.168.0.112)
		jsd		pts/1	2017-12-12	18:30	(192.168.0.112)

		$w
		系统运行时间,多少用户,用户登录多久,用户登录空闲时间,
		负载情况,各用户累计占用cpu时间,各用户当前之前的操作占用时间,当前登录用户正在执行什么操作
