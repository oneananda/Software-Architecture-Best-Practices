---

# **Principle of Least Privilege (PoLP)**

The **Principle of Least Privilege (PoLP)** is a foundational security concept that stipulates every user, program, or process should operate using the minimum privileges necessary to complete its tasks. By enforcing this principle, organizations can significantly reduce their attack surface and minimize the potential damage from accidental errors or malicious attacks.

---

## Amazon S3 PoLP

By default, Amazon S3 buckets and objects are **private**. This means:

- **Owner-Only Access:** When you create an S3 bucket or upload an object, only your AWS account (the bucket owner) has access to it.
- **No Public Access:** S3 does not expose your buckets or objects to the public unless you explicitly grant permissions through bucket policies, Access Control Lists (ACLs), or other access mechanisms.
- **Security-First Configuration:** This default privacy aligns with the Principle of Least Privilege, ensuring that only authorized users or services have access, reducing the risk of accidental exposure.

For example, if you create a new bucket named `my-private-bucket` and upload a file `document.pdf`, only your AWS account will have permissions to read or modify that file unless you change the settings to allow additional access.

---