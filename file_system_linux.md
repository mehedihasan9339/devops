# 🐧 লিনাক্স ফাইল সিস্টেম নেভিগেশন নোট (Linux File System Navigation)

[cite_start]এই নোটটি **Poridhi's Lab**-এর ওপর ভিত্তি করে তৈরি করা হয়েছে, যা তোমাকে লিনাক্স টার্মিনালে দক্ষ করে তুলবে [cite: 3, 5, 10]।

---

## 🏗️ ল্যাব সেটআপ (Lab Setup)
সবার আগে প্র্যাকটিস করার জন্য নিচের কমান্ডগুলো দিয়ে ডিরেক্টরি এবং কিছু ফাইল তৈরি করে নাও:
```bash
# মেইন ডিরেক্টরি তৈরি
mkdir -p ~/code/lab/projects/website
mkdir -p ~/code/lab/documents/reports
mkdir -p ~/code/lab/documents/notes

# স্যাম্পল ফাইল তৈরি
echo "Hello World" > ~/code/lab/projects/website/index.html
echo "Project Plan" > ~/code/lab/documents/reports/plan.txt
echo "Meeting Notes" > ~/code/lab/documents/notes/meeting.txt
echo "Todo List" > ~/code/lab/documents/notes/todo.txt
```
> [cite_start]এই স্ক্রিপ্টটি তোমার জন্য একটি সাজানো ফোল্ডার স্ট্রাকচার তৈরি করবে [cite: 36, 43]।

---

## 🛠️ প্রয়োজনীয় কমান্ডসমূহ (Essential Commands)

### 1. **pwd** (Print Working Directory)
* [cite_start]**কাজ:** তুমি বর্তমানে কোন ফোল্ডারে আছ তার পুরো ঠিকানা বা পাথ (Path) দেখায় [cite: 17, 59]।
* [cite_start]**উদাহরণ:** টার্মিনালে `pwd` লিখলে আউটপুট আসতে পারে `/root/code/lab` [cite: 60]।

### 2. **cd** (Change Directory)
* [cite_start]**কাজ:** এক ফোল্ডার থেকে অন্য ফোল্ডারে যাতায়াত করতে ব্যবহৃত হয় [cite: 18, 64]।
* **গুরুত্বপূর্ণ টিপস:**
    * [cite_start]`cd ~/code/lab`: হোম ডিরেক্টরির ভেতরে ল্যাব ফোল্ডারে যাওয়া [cite: 63]।
    * [cite_start]`cd ..`: বর্তমান ফোল্ডার থেকে এক ধাপ পেছনে বা উপরে যাওয়া [cite: 76, 81]।
    * [cite_start]**Absolute Path:** সরাসরি রুট (/) থেকে শুরু হওয়া ঠিকানা [cite: 76]।

### 3. **ls** (List)
* [cite_start]**কাজ:** একটি ফোল্ডারের ভেতরে কী কী ফাইল বা ফোল্ডার আছে তার তালিকা দেখায় [cite: 19, 94]।
* **ভিন্ন ভিন্ন ব্যবহার:**
    * [cite_start]`ls`: সাধারণ তালিকা [cite: 89]।
    * [cite_start]`ls -la`: লুকানো (Hidden) ফাইলসহ ডিটেইলস (পারমিশন, সাইজ, তারিখ) দেখা [cite: 91, 94]।
    * [cite_start]`ls /path/to/dir`: নিজে না গিয়েও অন্য ফোল্ডারের ভেতরটা দেখা [cite: 92, 93]।

### 4. **find** (Locate Files/Directories)
* [cite_start]**কাজ:** নির্দিষ্ট ফাইল বা ফোল্ডার খুঁজে বের করা [cite: 20, 123]।
* **ব্যবহার:**
    * `find . [cite_start]-name "*.txt"`: সব টেক্সট ফাইল খোঁজা [cite: 110, 125]।
    * `find . [cite_start]-type d`: শুধুমাত্র ডিরেক্টরি বা ফোল্ডার খোঁজা [cite: 112, 153]।
    * `find . [cite_start]-type f`: শুধুমাত্র ফাইল খোঁজা [cite: 113, 122]।

### 5. **grep** (Search Text Patterns)
* [cite_start]**কাজ:** ফাইলের ভেতরের লেখা বা কন্টেন্ট খুঁজে বের করা [cite: 21, 138]।
* **ব্যবহার:**
    * [cite_start]`grep -r "Meeting" ~/code/lab/documents`: ডকুমেন্ট ফোল্ডারের সব ফাইলের ভেতরে "Meeting" শব্দটি খোঁজা [cite: 135, 140]।
    * [cite_start]**-r অপশন:** এটি রিকার্সিভলি (Recursive) সব সাব-ফোল্ডারেও সার্চ করে [cite: 139]।

---

## 🏆 চ্যালেঞ্জ সলিউশন (Search Challenge)
[cite_start]ল্যাবের শেষে দেওয়া চ্যালেঞ্জগুলোর সমাধান নিচে দেওয়া হলো[cite: 146, 150]:

1.  **"List" শব্দটি আছে এমন সব ফাইল খোঁজা:**
    [cite_start]`grep -r "List" ~/code/lab` [cite: 151, 154]
2.  **ল্যাব ডিরেক্টরির সব .txt ফাইল খুঁজে বের করা:**
    [cite_start]`find ~/code/lab -name "*.txt"` [cite: 152, 155]
3.  **ল্যাব স্ট্রাকচারের সব ডিরেক্টরি (ফোল্ডার) লিস্ট করা:**
    [cite_start]`find ~/code/lab -type d` [cite: 153, 159]

---

## ⚠️ সাধারণ সমস্যা ও সমাধান (Troubleshooting)
* [cite_start]**Permission Denied:** `ls -la` দিয়ে চেক করো তোমার ফাইলটি পড়ার অনুমতি আছে কি না [cite: 167]।
* [cite_start]**No such file or directory:** বানান চেক করো এবং টাইপিং এড়াতে কিবোর্ডের **Tab** বাটন প্রেস করে অটো-কমপ্লিট করো [cite: 168]।
* [cite_start]**Command not found:** কমান্ডের সিনট্যাক্স বা বানান ঠিক আছে কি না নিশ্চিত হও [cite: 169]।
