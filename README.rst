
================
mboxattachments
================

This project is a replicate of mboxattachments, source: https://pypi.org/project/mboxattachments/.

I only downloaded and updated some lines of code according to my needs for extracting attachments from mbox files exported from gmail, please review recent commits.

this class works really well, i used python 3.8


mboxattachments is a Python class for extracting all embedded files in 
a group of emails.  It was developed to assist in the running of a 
photography club.  Members of the club would regularly send emails 
containing images to the club secretary.  The secretary would manually
save the attachments, organize those files, and prepare a show for the 
members.  The manual saving process was time consuming and error prone.

This utility allows downloading all the attachments in a set of emails
contained in an mbox file. Conveniently, gmail permits exporting emails
as mbox files

------------
Installation 
------------
On debian and Windows 7 the following is known to work

::

   pip install mboxattachments



---------
Running
---------
::

  mboxattachments --exportpath  images  emails.mbox

----------
Examples
----------

::

  mboxattachments --filter_from flur  --exportpath images emails.mbox
  
The above line will test all email messages in the file emails.mbox
to see the the senders name (FROM field) matches the regular expression 
flur.  If an mail matches, all of its attachments will be written to 
a file in the directory images. 

::

  mboxattachments --SQstart 1000  --exportpath images emails.mbox

The above command will save the attachments from every file in 
emails.bmox.  The file names will be of the form
SQ1000....,
SQ1001....,
SQ1003....


----------
Options
----------

::

  options:   specify output directory
             filter by sender
             filter by recipient 
             filter by date
             specify destination diretory for attachments
             set sequence number field starting value (default 0)  
             
  usage:
   mboxattachments [--help] [--version] [--debug] [--filter_from regexp] 
                   [--filter_to regexp] [--filter_date regexp]  
                   [--exportpath path] [--SQstart value]  input_mbox_file ...
             
  attachments are stored as separate files
  file names are of the form 
  <sequence number>-<email subject>-<email sender>-<file name of attachment>
    for example, a possible file name is 
    SQ0146-CellPhone - Action-johndoe@gmail.com-myPrettyPicture.jpg
    ------ ------------------ ----------------- -------------------
    seqnum    email subject     sender           file name in email
    
    
---------
Website
---------


http://www.chuck-jackson-photos.com/mboxattachments

download

http://www.chuck-jackson-photos.com/mboxattachments/mboxattachments-0.5.32.tar.gz

