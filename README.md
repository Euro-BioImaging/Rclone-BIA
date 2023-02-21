## Rclone-BIA

This repository facilitates exchange of data between your filesystem and your user space at 
the BioImage Archive using the Rclone package.

Rclone package is available for Unix-like systems as well as Windows. So the examples given below can
be run on the Unix shells as well as on the Windows CMD.

### Installation

Clone the repository: `git clone https://github.com/Euro-BioImaging/Rclone-BIA.git` \
Then cd to the directory of the repository and create a conda environment with the Rclone: \
`conda env create -f environment.yml`

### Examples: 

To show the contents of your secret directory on BIA, specify the path to the `new.rclone.conf` 
and replace `<YOUR-SECRET-DIRECTORY>` in the following command: \
`rclone --config /path/to/new.rclone.conf lsf ftp:/<YOUR-SECRET-DIRECTORY>`

To upload a single file to your BIA user space: \
`rclone --config /path/to/new.rclone.conf copy /local/path/filename ftp:/<YOUR-SECRET-DIRECTORY>/remote/path/` \
(Note that here you should not specify the remote file name as it will be the same as in the local file.) \

To upload a folder to your BIA user space: \
`rclone --config /path/to/new.rclone.conf sync /local/path/foldername ftp:/<YOUR-SECRET-DIRECTORY>/remote/path/foldername/` \
or \
`rclone --config /path/to/new.rclone.conf copy /local/path/foldername ftp:/<YOUR-SECRET-DIRECTORY>/remote/path/foldername/` \
(Note that in this case you should also include the folder name in the remote path)

To donwload a single file from your BIA user space: \
`rclone --config /path/to/new.rclone.conf copy ftp:/<YOUR-SECRET-DIRECTORY>/remote/path/filename /local/path` \
(Note that here you should not specify the file name as it will be the same as in the remote file.)

To download a folder from your BIA user space: \
`rclone --config /path/to/new.rclone.conf copy ftp:/<YOUR-SECRET-DIRECTORY>/remote/path/foldername /local/path/foldername` \

To delete a file or folder from your BIA user space: \
`rclone --config /path/to/new.rclone.conf purge ftp:/<YOUR-SECRET-DIRECTORY>/remote/path/foldername` \
