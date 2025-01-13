Create Hash values
<h2>Activity overview</h2>

As a security analyst, you’ll need to implement security controls to protect organizations against a range of threats.

That’s where hashing comes in. Previously, you learned that a hash function is an algorithm that produces a code that can’t be decrypted. Hash functions are used to uniquely identify the contents of a file so that you can check whether it has been modified. This code provides a unique identifier known as a hash value or digest.

For example, a malicious program may mimic an original program. If one code line is different from the original program, it produces a different hash value. Security teams can then identify the malicious program and work to mitigate the risk.

Many tools are available to compare hashes for various scenarios. But for a security analyst it’s important to know how to manually compare hashes.

In this lab activity, we’ll create hash values for two files and use Linux commands to manually examine the differences.

<h2>Scenario</h2>


In this scenario, we need to investigate whether two files are identical or different.

Here’s how you'll do this task: First, you’ll display the contents of two files and create hashes for each file. Next, you’ll examine the hashes and compare them.

Let’s hash some files!

<h2>Task 1. Generate hashes for files</h2>

The lab starts in your home directory, /home/analyst, as the current working directory. This directory contains two files file1.txt and file2.txt, which contain same data.

In this task, you need to display the contents of each of these files. You’ll then generate a hash value for each of these files and send the values to new files, which you’ll use to examine the differences in these values later.

1.Use the ls command to list the contents of the directory.

![image](https://github.com/user-attachments/assets/5f6b56d7-1fb6-4dee-9ec9-2087833fabad)

Two files, file1.txt and file2.txt, are listed.

2.Use the cat command to display the contents of the file1.txt file:

![image](https://github.com/user-attachments/assets/b0646696-85cb-4cbe-833e-eb94b21b3d03)

3.Use the cat command to display the contents of the file2.txt file:

![image](https://github.com/user-attachments/assets/9c2fff76-d30c-49b4-947c-c3a1e23e6a10)

4.Review the output of the two file contents:

![image](https://github.com/user-attachments/assets/46e421b0-5114-421f-8a35-dbfdc8c69825)

Although the contents of both files appear identical when you use the cat command, you need to generate the hash for each file to determine if the files are actually different.

5.Use the sha256sum command to generate the hash of the file1.txt file:

![image](https://github.com/user-attachments/assets/33ea949f-79c8-4038-b3fa-fe34f92a71fc)

6.Use the sha256sum command to generate the hash of the file2.txt file:

![image](https://github.com/user-attachments/assets/81b82e7e-537f-4b0a-b417-4baa001cc526)

7.Review the generated hashes of the contents of the two files:

![image](https://github.com/user-attachments/assets/2567638f-4086-4a91-872b-12870c7738b7)

<h2>Task 2. Compare hashes</h2>

In this task, you’ll write the hashes to two separate files and then compare them to find the difference.

1.Use the sha256sum command to generate the hash of the file1.txt file, and send the output to a new file called file1hash:

![image](https://github.com/user-attachments/assets/26ed462a-bcc6-436e-811d-64284282a646)

You now need to complete the same step for the file2.txt file.

2.Use the sha256sum command to generate the hash of the file2.txt file, and send the output to a new file called file2hash:

![image](https://github.com/user-attachments/assets/ced0c2c0-6041-48f0-8627-b5e7fd886c0c)

Now, you should have two hashes written to separate files. The first hash was written to the file1hash file, and the second hash was written to the file2hash file.

You can manually display and compare the differences.

3.Use the cat command to display the hash values in the file1hash and file2hash files.

![image](https://github.com/user-attachments/assets/fc32d3ff-37d4-40a3-8e50-7e3808693ead)

4.Inspect the output and note the difference in the hash values.
Now, you can use the cmp command to compare the two files byte by byte. If a difference is found, the command reports the byte and line number where the first difference is found.

5.Use the cmp command to highlight the differences in the file1hash and file2hash files:

![image](https://github.com/user-attachments/assets/011d2ee4-3d94-4f74-b163-4c836e68e644)

6.Review the output, which reports the first difference between the two files:

![image](https://github.com/user-attachments/assets/fa0b55c5-66b7-41d6-b451-dfe32e2e1df2)

