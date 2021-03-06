	nautilus  //打开对应目录
	rm -rf   //强制删除
	sudo  //管理员权限
	vi    //编写文档
	gedit //用gedit编写文档
	cd   //进入相应目录

#Dos命令	

---
	md  建立子目录命令
		格式：MD[盘符：][路径名][子目录名]
		类型：内部命令
		md f:\test\test1
		使用说明：
		（1）“盘符”：指定要建立子目录的磁盘驱动器字母，若省略，则为当前驱动器；
		（2）“路径名”：要建立的子目录的上级目录名，若缺省则建在当前目录下。
		
---
	cd 改变当前目录
		格式：CD[盘符：][路径名][子目录名]
		类型：内部命令
		cd f:\test\test1
		使用说明：
		（1）如果省略路径和子目录名则显示当前目录；
		（2）如采用“CD\”格式，则退回到根目录；
		（3）如采用“CD..”格式则退回到上一级目录。

---
	rd 删除子目录命令
		格式：RD[盘符：][路径名][子目录名]
		类型：内部命令
		rd f:\test\test1
		使用说明：
		（1）子目录在删除前必须是空的，也就是说需要先进入该子目录，使用DEL（删除文件的命令）将其子目录下的文件删空，然后再退回到上一级目录，用RD命令删除该了目录本身；　
		（2）不能删除根目录和当前目录。

---
	dir 显示磁盘目录
		格式：DIR [盘符][路径名][/P][/W]
		rd f:\test\test1/p/w
		类型：内部命令
		使用说明：
		（1）/P的使用；当欲查看的目录太多，无法在一屏显示完屏幕会一直往上卷，不容易看清，加上/P参数后，屏幕上会分面一次显示23行的文件信息，然后暂停，并提示：Pressany key to continue
		（2）/W的使用：加上/W只显示文件名，至于文件大小及建立的日期和时间则都省略。加上参数后，每行可以显示五个文件名。

---
	PATH 路径设置命令
		格式：PATH[盘符1：][路径1];[盘符2：][路径2]…（设定可执行文件的搜索路径）
		类型：内部命令
		使用说明：
		（1）功能：设备可执行文件的搜索路径，只对文件有效。
		（2）当运行一个可执行文件时，DOS会先在当前目录中搜索该文件，若找到则运行之；若找不到该文件，则根据PATH命令所设置的路径，顺序逐条地到目录中搜索该文件；　
		（3）PATH命令中的路径，若有两条以上，各路径之间以一个分号“；”隔开；
		（4）PATH：（取消所有路径）　PATH（显示目前所设的路径）　　

---
	TREE 显示磁盘目录结构命令
		格式：TREE[盘符：][/F][>PRN]
		类型：外部命令
		使用说明：
		（1）功能：显示指定驱动器上所有目录路径和这些目录下的所有文件名。
		（2）使用/F参数时显示所有目录及目录下的所有文件，省略时，只显示目录，不显示目录下的文件；　
		（3）选用＞PRN参数时，则把所列目录及目录中的文件名打印输出。

---
	DELTREE 删除整个目录命令
		格式：DELTREE[盘符：][路径名]
		类型：外部命令
		使用说明：
		（1）功能：将整个目录及其下属子目录和文件删除。
		（2）该命令可以一步就将目录及其下的所有文件、子目录、更下层的子目录一并删除，而且不管文件的属性为隐藏、系统或只读，只要该文件位于删除的目录之下，DELTREE都一视同仁，照删不误。使用时务必小心。

---
##磁盘操作类命令
	formAT 磁盘格式化命令
		格式：formAT [盘符：][/S][/4][/Q]
		类型：外部命令
		使用说明：
		（1）功能：对磁盘进行格式化，划分磁道和扇区；同时检查出整个磁盘上有无带缺陷的磁道，对坏道加注标记；建立目录区和文件分配表，使磁盘作好接收DOS的准备。
		（2）命令后的盘符不可缺省，若对硬盘进行格式化，则会如下列提示：WARNING:ALL DATA ON NON——REMOVABLE DISK　DRIVE C:WILL BE LOST ！　Proceed with format (Y/N)？　（警告：所有数据在C盘上，将会丢失，确实要继续格式化吗？）　
		（3）若是对软盘进行格式化，则会如下提示：Insert mew diskette for drive A;　and press ENTER when ready…　（在A驱中插入新盘，准备好后按回车键）。　
		（4）选用[/S]参数，将把DOS系统文件IO.SYS、MSDOS.SYS及COMMAND.COM复制到磁盘上，使该磁盘可以做为DOS启动盘。若不选用/S参数，则格式化后的磙盘只能读写信息，而不能做为启动盘；　（5）选用[/4]参数，在1.2MB的高密度软驱中格式化360KB的低密度盘；　
		（6）选用[/Q]参数，快速格式化，这个参数并不会重新划分磁盘的磁道貌岸然和扇区，只能将磁盘根目录、文件分配表以及引导扇区清成空白，因此，格式化的速度较快。　
		（7）选用[/U]参数，表示无条件格式化，即破坏原来磁盘上所有数据。不加/U，则为安全格式化，这时先建立一个镜象文件保存原来的FAT表和根目录，必要时可用UNFORMAT恢复原来的数据。　

---	
	UNformAT 恢复格式化命令
		格式：UNformAT[盘符][/L][/U][/P][/TEST]
		类型：外部命令
		使用说明：
		（1）功能：用于将被“非破坏性”格式化的磁盘恢复。根目录下被删除的文件或子目录及磁盘的系统扇区（包括FAT、根目录、BOOT扇区及硬盘分区表）受损时，也可以用UNformAT来抢救。
		（2）选用/L参数列出找到的子目录名称、文件名称、大孝日期等信息，但不会真的做formAT工作。　
		（3）选用/P参数将显示于屏幕的报告（包含/L参数所产生的信息）同时也送到打印机。运行时屏幕会显示：“Print out willbe sent to LPT1”　
		（4）选用/TEST参数只做模拟试验（TEST）不做真正的写入动作。使用此参数屏幕会显示：“Simulation only”　
		（5）选用/U参数不使用MIRROR映像文件的数据，直接根据磁盘现状进行UNformAT。　
		（6）选用/PSRTN；修复硬盘分区表。　若在盘符之后加上/P、/L、/TEST之一，都相当于使用了/U参数，UNformAT会“假设”此时磁盘没有MIRROR映像文件。　
		（7）UNformAT对于刚formAT的磁盘，可以完全恢复，但formAT后若做了其它数据的写入，则UNformAT就不能完整的救回数据了。UNformAT并非是万能的，由于使用UNformAT会重建FAT与根目录，所以它也具有较高的危险性，操作不当可能会扩大损失，如果仅误删了几个文件或子目录，只需要利用UNDELETE就够了。

---
	CHKDSK 检查磁盘当前状态命令
		格式：CHKDSK [盘符：][路径][文件名][/F][/V]
		类型：外部命令
		使用说明：
		（1）功能：显示磁盘状态、内存状态和指定路径下指定文件的不连续数目。　
		（2）选用[文件名]参数，则显示该文件占用磁盘的情况；
		（3）选[/F]参数，纠正在指定磁盘上发现的逻辑错误；　
		（4）选用[/V]参数，显示盘上的所有文件和路径。

---
	DISKCOPY 整盘复制命令
		格式：DISKCOPY[盘符1：][盘符2：]
		类型：外部命令
		使用说明：
		（1）功能：复制格式和内容完全相同的软盘。
		（2）如果目标软盘没有格式化，则复制时系统自动选进行格式化。　
		（3）如果目标软盘上原有文件，则复制后将全部丢失。　
		（4）如果是单驱动器复制，系统会提示适时更换源盘和目标盘，请操作时注意分清源盘和目标盘。

---
	LABEL 建立磁盘卷标命令
		格式：LABEL[盘符：][卷标名]
		类型：外部命令
		使用说明：
		（1）功能：建立、更改、删除磁盘卷标。
		（2）卷标名为要建立的卷标名，若缺省此参数，则系统提示键入卷标名或询问是否删除原有的卷标名；
		（3）卷标名由1至11个字符组成。

---
	VOL 显示磁盘卷标命令
		格式：VOL[盘符：]
		类型：内部命令
		使用说明：
		（1）功能：查看磁盘卷标号。
		（2）省略盘符，显示当前驱动器卷标。

---
	SCANDISK 检测、修复磁盘命令
		格式：SCANDISK[盘符1：][盘符2：]..[/ALL]　
		类型：外部命令
		使用说明：
		（1）功能：检测磁盘的FAT表、目录结构、文件系统等是否有问题，并可将检测出的问题加以修复。　
		（2）SCANDISK适用于硬盘和软盘，可以一次指定多个磁盘或选用[/ALL]参数指定所有的磁盘；　
		（3）可自动检测出磁盘中所发生的交叉连接、丢失簇和目录结构等逻辑上的错误，并加以修复。

---
	DEFRAG 重整磁盘命令
		格式：DEFRAG[盘符：][/F]
		类型：外部命令
		使用说明：
		（1）功能：整理磁盘，消除磁盘碎块。
		（2）选用/F参数，将文件中存在盘上的碎片消除，并调整磁盘文件的安排，确保文件之间毫无空隙。从而加快读盘速度和节省磁盘空间。

---
	SYS 系统复制命令
		格式：SYS[盘符：]
		类型：外部命令
		使用说明：
		（1）将当前驱动器上的DOS系统文件IO.SYS,MSDOS.SYS和COMMAND.COM 传送到指定的驱动器上。
		（2）如果磁盘剩余空间不足以存放系统文件，则提示：No roomfor on destination disk.　

---
##文件操作类命令
	 COPY 文件复制命令
		格式：COPY [源盘][路径][源文件名][目标盘][路径][目标文件名]
		类型：内部命令
		使用说明：
		（1）功能：拷贝一个或多个文件到指定盘上。
		（2）COPY是文件对文件的方式复制数据，复制前目标盘必须已经格式化；　
		（3）复制过程中，目标盘上相同文件名称的旧文件会被源文件取代；　
		（4）复制文件时，必须先确定目标般有足够的空间，否则会出现；insufficient的错误信息，提示磁盘空间不够；　
		（5）文件名中允许使用通配举“*”“？”，可同时复制多个文件；　
		（6）COPY命令中源文件名必须指出，不可以省略。　
		（7）复制时，目标文件名可以与源文件名相同，称作“同名拷贝”此时目标文件名可以省略；　
		（8）复制时，目标文件名也可以与源文件名不相同，称作“异名拷贝”，此时，目标文件名不能省略；　
		（9）复制时，还可以将几个文件合并为一个文件，称为“合并拷贝”，格式如下：COPY；[源盘][路径][源文件名1][源文件名2]…[目标盘][路径]〈目标文件名〉；　
		（10）利用COPY命令，还可以从键盘上输入数据建立文件，格式如下：COPY CON [盘符：][路径]〈文件名〉；　
		（11）COPY命令的使用格式，源文件名与目标文件名之间必须有空格！　
		
---
	XCOPY 目录复制命令
		格式：XCOPY [源盘：][源路径名][目标盘符：][目标路径名][/S][/V][/E]
		类型：外部命令
		使用说明：
		（1）功能：复制指定的目录和目录下的所有文件连同目录结构。
		（2）XCOPY是COPY的扩展，可以把指定的目录连文件和目录结构一并拷贝，但不能拷贝隐藏文件和系统文件；
		（3）使用时源盘符、源目标路径名、源文件名至少指定一个；　
		（4）选用/S时对源目录下及其子目录下的所有文件进行COPY。除非指定/E参数，否则/S不会拷贝空目录，若不指定/S参数，则XCOPY只拷贝源目录本身的文件，而不涉及其下的子目录；　
		（5）选用/V参数时，对的拷贝的扇区都进行较验，但速度会降低。

---
	TYPE 显示文件内容命令
		格式：TYPE[盘符：][路径][文件名]
		类型：内部命令
		使用说明：
		（1）功能：显示ASCII码文件的内容。　
		（2）显示由ASCII码组成的文本文件，对EXE.COM等为扩展名的文件，其显示的内容是无法阅读的，没有实际意义；　
		（3）该命令一次只可以显示一个文件的内容，不能使用通配符；　
		（4）如果文件有扩展名，则必须将扩展名写上；　
		（5）当文件较长，一屏显示不下时，可以按以下格式显示；TYPE[盘符：][路径][文件名]|MORE，MORE为分屏显示命令，使用些参数后当满屏时会暂停，按任意键会继续显示。　
		（6）若需将文件内容打印出来，可用如下格式：　TYPE[盘符：][路径]〈文件名〉，＞PRN　此时，打印机应处于联机状态。

---
	REN 文件改名命令
		格式：REN[盘符：][路径][旧文件名][新文件名]
		类型：内部命令
		使用说明：　
		（1）功能：更改文件名称
		（2）新文件名前不可以加上盘符和路径，因为该命令只能对同一盘上的文件更换文件名；　
		（3）允许使用通配符更改一组文件名或扩展名。

---
	FC 文件比较命令
		格式：FC[盘符：][路径名][文件名][盘符：][路径名][文件名][/A][/B][/C][/N]
		类型：外部命令
		使用说明：
		（1）功能：比较文件的异同，并列出差异处。
		（2）选用/A参数，为ASCII码比较模式；　
		（3）选用/B参数，为二进制比较模式；　
		（4）选用/C参数，将大小写字符看成是相同的字符。　
		（5）选用/N参数，在ASCII码比较方式下，显示相异处的行号。

---
	Attrib 修改文件属性命令
		格式：ATTRIB[文件名][R][——R][A][——A][H][——H][——S]
		类型：外部命令。
		使用说明：　
		（1）功能：修改指定文件的属性。
		（2）选用R参数，将指定文件设为只读属性，使得该文件只能读取，无法写入数据或删除；选用——R参数，去除只读属性；　
		（3）选用A参数，将文件设置为档案属性；选用——A参数，去除档案属性；　 
		（4）选用H参数，将文件调协为隐含属性；选用——H参数，去隐含属性；　
		（5）选用S参数，将文件设置为系统属性；选用——S参数，去除系统属性；　 
		（6）选用/S参数，对当前目录下的所有子目录及作设置。　

---
	DEL 删除文件命令
		格式：DEL[盘符：][路径][文件名][/P]
		类型：内部命令
		使用说明：　
		（1）功能：删除指定的文件
		（2）选用/P参数，系统在删除前询问是否真要删除该文件，若不使用这个参数，则自动删除；　
		（3）该命令不能删除属性为隐含或只读的文件；
		（4）在文件名称中可以使用通配符；
		（5）若要删除磁盘上的所有文件（DEL*·*或DEL·），则会提示：(Arey ou sure？）（你确定吗？）若回答Y，则进行删除，回答N，则取消此次删除作业。

---
	UNDELETE 恢复删除命令 
		格式：UNDELETE[盘符：][路径名][文件名][/DOS]/LIST][/ALL]
		类型：外部命令。
		使用说明：
		（1）功能：恢复被误删除命令
		（2）使用UNDELETE可以使用“*”和“？”通配符。  
		（3）选用/DOS参数根据目录里残留的记录来恢复文件。由于文件被删除时，目录所记载斩文件名第一个字符会被改为E5，DOS即依据文件开头的E5和其后续的字符来找到欲恢复的文件，所以，UNDELETE会要求用户输入一个字符，以便将文件名字补齐。但此字符不必和原来的一样，只需符合DOS的文件名规则即可。  
		（4）选用/LIST只“列出”符合指定条件的文件而不做恢复，所以对磁盘内容完全不会有影响。  
		（5）选用/ALL自动将可完全恢复的文件完全恢复，而不一一地询问用户，使用此参数时，若UNDELTE利用目录里残留的记录来将文件恢复，则会自动选一个字符将文件名补齐，并且使其不与现存文件名相同，选用字符的优选顺序为：#%——0000123456789A~Z。
		（6）UNDELETE还具有建立文件的防护措施的功能

---
##其它命令
	CLS 清屏幕命令
		格式：CLS
		类型：内部命令
		使用说明：
		（1）功能：清除屏幕上的所有显示，光标置于屏幕左上角。

---
	 VER 查看系统版本号命令
		格式：VER
		类型：内部命令
		使用说明：
		（1）功能：显示当前系统版本号

---
	DATA 日期设置命令
		格式：DATE[mm——dd——yy]
		类型：内部命令
		使用说明：
		（1）功能：设置或显示系统日期。  
		（2）省略[mm——dd——yy]显示系统日期并提示输入新的日期，不修改则可直接按回车键，[mm——dd——yy]为“月月——日日——年年”格式；  
		（3）当机器开始启动时，有自动处理文件（AUTOEXEC.BAT）被执行，则系统不提示输入系统日期。否则，提示输入新日期和时间。

---
	TIME 系统时钟设置命令
		格式：TIME[hh：mm：ss：xx] 
		类型：内部命令 
		使用说明：
		（1）功能：设置或显示系统时期。
		（2）省略[hh：mm：ss：xx]，显示系统时间并提示输入新的时间，不修改则可直接按回车键，[hh：mm：ss：xx]为“小时：分钟：秒：百分之几秒”格式；  
		（3）当机器开始启动时，有自动处理文件（AUTOEXEC.BAT）被执行，则系统不提示输入系统日期。否则，提示输入新日期和时间。 

---
	MEM 查看当前内存状况命令
		格式：MEM[/C][/F][/M][/P]
		类型：外部命令
		使用说明： 
		（1）功能：显示当前内存使用的情况 
		（2）选用/C参数列出装入常规内存和CMB的各文件的长度，同时也显示内存空间的使用状况和最大的可用空间；  
		（3）选用/F参数分别列出当前常规内存剩余的字节大小和UMB可用的区域及大小；   
		（4）选用/M参数显示该模块使用内存地地址、大小及模块性质；  
		（5）选用/P参数指定当输出超过一屏时，暂停供用户查看。  

---
	MSD 显示系统信息命令 
		格式：MSD[/I][/B][/S]  
		类型：外部命令
		使用说明：  
		（1）功能：显示系统的硬件和操作系统的状况。
		（2）选用/I参数时，不检测硬件；  
		（3）选用/B参数时，以黑白方式启动MSD；  
		（4）选用/S参数时，显示出简明的系统报告。