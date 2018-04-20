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
		
		
	8.压缩/解压缩命令(.gz .zip .rar)

		(1)gzip 文件名		[压缩]	
			gunzip 文件名		[解压缩]	
							[gzip只能压缩文件,不保留原文件]

		(2)tar -cvfz 目标文件夹名称.tar.gz 原文件夹名称		[压缩]	

					[-c 打包]
					[-v 显示详细信息]
					[-f 指定文件名称]
					[-z 打包同时压缩]

			tar -xvfz 要解压的文件名	   [解压]
					
					[-x 解包]

		(3)zip [-r] 新文件名	旧文件名/目录		[压缩]
					
					[-r 压缩目录]

			unzip 解压缩文件名		[解压缩]
		
		(4)bzip2 [-k] 要压缩的文件名		[压缩]

						[-k 压缩后保留原文件]

				结合压缩:tar -cjf 目标文件名.tar.bz2 原文件名

			bunzip2 [-k] 压缩文件

						[-k 解压后保留原文件]

				结合解压缩:tar -xjf 要解压的文件名.tar.bz2
