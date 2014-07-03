# RPM Commands

###List installed RPM packages on local machine

	rpm -qa

###Export all files deployed from any package to a file

be careful because of >> = append

	for i in $(rpm -qa);do rpm -ql "$i" >> rpm_output.txt; done
