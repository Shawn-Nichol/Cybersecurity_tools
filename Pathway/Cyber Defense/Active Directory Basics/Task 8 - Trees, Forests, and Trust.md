
## Task 8 Trees, Forests, and Trusts
The domain can be split into subdomains. For example, if there was a branch in the US and the UK, you could build a tree with a root domain and then two subdomains, so you distribute unique OUs. 


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/d3356401-abe9-4a76-9a0f-2e33058aa79c)

The union of several trees with different namespaces into the same network is known as a forest. 


![image](https://github.com/Shawn-Nichol/TryHackMe/assets/30714313/c4597714-aabb-4d77-b55a-81c6e7d3d090)

**Trust Relationships**
A trust relationship between domains allows you to authorize a user from Domain 1 to access resources from Domain 2.


Question: What is a group of Windows domains that share the same namespace called?
Answer: tree

Question: What should be configured between two domains for a user in Domain A to access a resource in DOmain B?
Answer: A trust Relationship.
