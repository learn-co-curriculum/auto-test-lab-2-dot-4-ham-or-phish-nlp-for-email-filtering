# 🔎 Lab: 2.4 HAM or PHISH? - NLP for Email Filtering 

<p><em>Select the tabs to navigate through the content.</em></p>
<div style="margin: 1em 0%; padding: 10px 15px; border: 2px solid #A2AAAD; background: #ffffff; font-size: 100%; overflow: auto;">
<div class="enhanceable_content tabs">
<ul>
<li><a href="#fragment-1">Introduction</a></li>
<li><a href="#fragment-2">Email Filtering</a></li>
<li><a href="#fragment-3">Rule Based Algorithms</a></li>
<li><a href="#fragment-4">Machine Based Algorithms</a></li>
<li><a href="#fragment-5">Modern Email Filters</a></li>
<li><a href="#fragment-6">What is Pseudo-Code?</a></li>
<li><a href="#fragment-7">Email Classification Script</a></li>
<li><a href="#fragment-8">Procedure</a></li>
<li><a href="#fragment-9">Summary</a></li>
</ul>
<div id="fragment-1" style="overflow: auto:;">
<h3>Introduction</h3>
<p>Spam emails, which are unsolicited and often bulk messages sent to a large number of recipients, started becoming a problem in the late 1990s. These emails typically contained advertisements, scams, or other forms of unwanted content. Over time, spam became a widespread issue, leading to the development of spam filters and anti-spam measures.</p>
<p>Phishing attacks, on the other hand, began to emerge in the early 2000s. Phishing refers to a type of cyber attack where malicious actors impersonate trustworthy entities or organizations to deceive recipients into disclosing sensitive information, such as passwords, credit card details, or personal data. Phishing emails are designed to appear legitimate and often employ social engineering techniques to trick recipients into taking action that benefits the attackers.</p>
<p>Phishing attacks became increasingly prevalent with the rise of online banking, e-commerce, and other online services that require users to provide sensitive information. Attackers realized that by impersonating trusted entities, they could gain access to valuable data or exploit users for financial gain.</p>
<p>While spam and phishing are distinct concepts, they are often intertwined. Let’s compare the two:</p>
<ul>
<li>Phishing attacks may be delivered through spam emails, leveraging the large volume and distribution capabilities of spam campaigns to reach a broader audience.</li>
<li>However, not all spam emails are phishing attempts, as spam can also include other types of unwanted or irrelevant content.</li>
<li>Since their emergence, both spam and phishing have continued to evolve and adapt to technological advancements and countermeasures.</li>
<li>Organizations and individuals employ various strategies, such as email filters, user awareness training, and security measures, to combat both spam and phishing and protect against their threats.</li>
</ul>
<p>In this exercise, you will use your knowledge of language patterns used by malicious actors and natural language processing techniques that were introduced in previous lessons to classify emails as HAM (legitimate emails) or PHISH (malicious emails). Creating labeled datasets such as these allows us to train models that can classify millions of emails, using the patterns extracted from just a small subset of known malicious emails.</p>
<h4>Lesson Objectives</h4>
<p>By the end of this lesson, you will be able to&nbsp;</p>
<ul>
<li>Distinguish between rule-based and machine learning algorithms</li>
<li>Identify rules to classify suspicious emails</li>
<li>Determine the steps to build an email classifier</li>
</ul>
</div>
<div id="fragment-2" style="overflow: auto:;">
<h3>Email Filtering</h3>
<p>Email filtering is a process in which incoming and outgoing emails are analyzed and categorized based on predefined criteria or rules. The purpose of email filtering is to identify and handle emails based on their content, sender, recipient, or other attributes. Filtering can be performed by email servers, email clients, or dedicated email security systems.</p>
<p>In practice, email filtering systems often employ a combination of rule-based and machine learning techniques. Rule-based filters may be used as an initial line of defense to quickly identify and block obvious spam or phishing attempts based on known patterns. Machine learning models can then be employed to further analyze and classify emails based on more complex features and evolving patterns.</p>
<p>In this lesson, we will discuss rule-based and machine learning techniques for email detection. Then, you will practice classifying emails as HAM or PHISH based on your knowledge of phishing email analysis techniques from the previous lesson. Through this exercise, you will learn all the necessary steps for building an email classifier.</p>
</div>
<div id="fragment-3" style="overflow: auto:;">
<h3>Rule-Based Algorithms</h3>
<p>Early email filters utilized user-defined rule-based approaches. Users could set up filters based on specific keywords, email addresses, or other patterns to sort incoming emails into different folders or mark them as spam. These filters relied on manually created rules and lacked sophistication but provided some level of control over unwanted emails.</p>
<p>Rule-based email filtering algorithms rely on predefined sets of rules and conditions to filter emails. These rules are typically created based on known patterns, keywords, or characteristics associated with spam or phishing emails. The filter applies these rules to incoming emails and flags or categorizes them accordingly.</p>
<p>To combat spam, blacklists, and whitelists were introduced. Blacklists contained known spam sources or email addresses, and emails from these sources were blocked or flagged as spam. Conversely, whitelists allowed users to specify trusted email addresses, ensuring that emails from those sources would always be delivered to the inbox.</p>
</div>
<div id="fragment-4" style="overflow: auto:;">
<h3>Machine Learning Algorithms</h3>
<p>In the early 2000s, Bayesian filtering emerged as a more advanced technique. Bayesian filters used statistical algorithms to analyze the textual content of emails and determine the probability of an email being spam based on learned patterns from a training dataset. This approach improved spam detection accuracy by considering the frequency and co-occurrence of words and phrases.</p>
<p>Machine learning approaches for email filtering involve training models on labeled datasets to automatically learn patterns and features indicative of spam or phishing emails. These models can leverage various algorithms, such as decision trees, Naive Bayes, support vector machines (SVM), or more advanced techniques like deep learning with neural networks. The models extract relevant features from email content, metadata, and other contextual information to make predictions about the email's category.</p>
<p>The training process involves providing the model with a dataset of labeled emails, where each email is labeled as spam (emails that are a nuisance), ham (emails that are legitimate), or phish (emails that are malicious). The model learns the patterns and relationships in the data and generalizes them to make predictions on new, unseen emails. Machine learning-based filters have the advantage of adaptability and can learn from evolving spam or phishing tactics. They can improve their accuracy over time as they encounter more examples and update their models.</p>
<p>By combining rule-based algorithms and machine learning techniques, email filters aim to provide a robust and effective solution for detecting and filtering spam and phishing emails, enhancing email security, and reducing the risk to end-users.</p>
</div>
<div id="fragment-5" style="overflow: auto:;">
<h3>Modern Email Filters</h3>
<p>Modern email filters also employ behavioral analysis and heuristics to detect spam, phishing, and other email-based threats. These filters analyze patterns, sender reputation, email headers, and other contextual information to identify suspicious activities, such as large-scale email campaigns or attempts to deceive users. Heuristics-based filters make use of predefined rules and algorithms to evaluate email content and determine its likelihood of being spam or malicious.</p>
<p>Today, effective email filtering systems often combine multiple techniques and approaches. They employ a combination of rule-based filtering, machine learning algorithms, blacklists, whitelists, behavioral analysis, and authentication mechanisms. This integration allows for more accurate and comprehensive detection of spam, phishing attempts, malware, and other email threats.</p>
</div>
<div id="fragment-6" style="overflow: auto:;">
<h3>What is Pseudo-Code?</h3>
<p>In this exercise, you will be tasked with writing a script in pseudo-code that will classify emails as HAM, SPAM, or PHISH. If you are unfamiliar with programming, this might seem like an intimidating task, but the beauty of writing in pseudo-code is that it allows you to articulate the rules that the program should execute in an approachable way.</p>
<p>Pseudo-code is a simplified and human-readable notation that represents the steps and logic of a computer program or algorithm. It uses a combination of plain English language and programming-like constructs to outline the sequence of operations, decision-making processes, loops, and other control structures involved in the program.</p>
<p>Here is a simplified example of a pseudo-code for dispensing a soda from a vending machine:</p>
<p style="padding-left: 40px;"><code><strong>While</strong> <span style="color: #3598db;"><strong style="color: #065387;">Coin?</strong></span> <strong>=</strong> “Yes” <strong>then</strong> <span style="color: #e67e23;"><strong style="color: #764016;">Action?</strong></span> = "Dispense Soda"</code></p>
<p style="padding-left: 40px;"><code><strong>Else:</strong> "Pass"</code></p>
<em><span style="font-size: 100%; color: var(--ic-brand-font-color-dark); font-family: inherit;">In English, we would interpret this as "When a coin is present in the machine, dispense a soda. Otherwise, do nothing."</span></em>
<p><span style="font-size: 100%; color: var(--ic-brand-font-color-dark); font-family: inherit;">Pseudocode is not meant to be executed by a computer; instead, it serves as a blueprint for programmers to design and communicate their algorithms. There are no hard and fast rules about the conventions that you use to convey your idea, as long as it is clear to the reader. It is simply a way to help programmers think through the problem-solving process and plan their code implementation before writing the actual code in a specific programming language.</span></p>
</div>
<div id="fragment-7" style="overflow: auto:;">
<h3>Email Classification Script</h3>
<p>To keep our example simple, we are going to look for three specific types of flags in email text that suggest phishing. Keep in mind that in a professional context, email classification uses a more complex combination of rule-based and machine learning algorithms.</p>
<p style="padding-left: 40px;"><strong>Flag 1 - Potential Phishing Emails</strong><br>Are there keywords or phrases like “urgent”, “important”, or “click here”?<br>Does the email contain terms like “Forgot Password?”</p>
<p style="padding-left: 40px;"><strong>Flag 2 - Identifying Suspicious Entities/Links</strong><br>Are any of the links in the email URLs for banks or credit card companies?&nbsp;<br>Is the name of banks or similar organizations mentioned in the text?</p>
<p style="padding-left: 40px;"><strong>Flag 3 - Typos and Grammatical Errors</strong><br>Are there obvious misspellings and mistakes in the text?</p>
<p>In addition, there are rules about the sequence of events that occur.</p>
<ol style="list-style-type: decimal;">
<li>New emails should be quarantined and checked before they are moved to the inbox.</li>
<li>The text should be preprocessed before using techniques like sentiment analysis or NER.</li>
</ol>
<p>With these rules in mind,&nbsp; you will order the pseudo-code lines in the exercise below so that they are in the correct order to classify the emails using the rules described here and your knowledge of NLP, cyber security, and email filtering.&nbsp;</p>
</div>
<ol style="list-style-type: upper-alpha;">
<li id="fragment-8">
<h3>Procedure</h3>
<p>Work through each of the parts below and order the steps of the email filtering process for each part.</p>
<h4>Part 1 - Preprocess Text</h4>
<p><strong>Task:</strong> Preprocess the text and output a tokenized version that will be represented by the variable <code>TOKEN_TEXT</code>.</p>
<p><em><strong>Order each of the steps (A-E) in the correct order to accomplish the task.</strong></em></p>
<ol style="list-style-type: upper-alpha;">
<li><code>If COUNT(QUARANTINE) &gt; 0 then CHECK_EMAIL = YES</code></li>
<li><code>For each EMAIL in QUARANTINE apply CHECK_EMAIL(EMAIL). If CHECK_EMAIL(EMAIL) then EMAIL_TEXT = EXTRACT_TEXT(EMAIL)</code></li>
<li><code>While EMAIL = NEW, move EMAIL to QUARANTINE</code></li>
<li><code>TOKEN_TEXT = YES</code></li>
<li><code>If EMAIL_TEXT = YES then TOKEN_TEXT = TOKENIZE(EMAIL_TEXT)</code>&nbsp;</li>
</ol>
<details style="margin-bottom: 2.5rem;">
<summary style="display: inline-block; background: #394a58; border: 1px solid #8A8B99; padding: 0.5rem 0.75rem; cursor: pointer;"><span style="color: #ffffff;">Select for Part 1 </span></summary>
<ol style="list-style-type: decimal;">
<li><code>While EMAIL = NEW, move EMAIL to QUARANTINE</code></li>
<li><code>If COUNT(QUARANTINE) &gt; 0, CHECK_EMAIL = YES</code></li>
<li><code>For each EMAIL in QUARANTINE apply CHECK_EMAIL(EMAIL). If CHECK_EMAIL(EMAIL) then EMAIL_TEXT = EXTRACT_TEXT(EMAIL)</code></li>
<li><code>If EMAIL_TEXT = YES then TOKEN_TEXT = TOKENIZE(EMAIL_TEXT)</code></li>
<li><code>TOKEN_TEXT = YES</code></li>
</ol>
</details>
<h4>Part 2 - NER for Suspicious Entities and Links</h4>
<p><strong>Task:</strong> Label each preprocessed email as <code>SUSPICIOUS_ENT = YES</code> or <code>SUSPICIOUS_LINK = YES</code> based on the rules that we articulated above for <strong>Flag 2: <em>Are any of the links in the email URLs for banks or credit card companies? Is the name of banks or similar organizations mentioned in the text?</em></strong></p>
<p><em><strong>Order each of the steps (A-E) in the correct order to accomplish the task.</strong></em></p>
<ol style="list-style-type: upper-alpha;">
<li><code>If ANY(TOKEN in TOKEN_TEXT) starts with ANY(“Bank of”) or ends with ANY(“Bank”, “Credit Union”) then SUSPICIOUS ENT = YES</code></li>
<li><code>If TOKEN_TEXT = YES then NER(TOKEN_TEXT)</code></li>
<li><code>If ANY(TOKEN in TOKEN_TEXT) = URL, CHECK_PATTERNS(URL)</code></li>
<li><code>If NER(TOKEN_TEXT) then CHECK_PATTERNS(TOKEN_TEXT)</code></li>
<li><code>If ANY(TOKEN in URL) starts with ANY(“Bank of”) or ends with ANY(“Bank”, “Credit Union”) then SUSPICIOUS LINK = YES</code></li>
</ol>
<details style="margin-bottom: 2.5rem;">
<summary style="display: inline-block; background: #394a58; border: 1px solid #8A8B99; padding: 0.5rem 0.75rem; cursor: pointer;"><span style="color: #ffffff;">Select for Part 2 </span></summary>
<ol style="list-style-type: decimal;">
<li><code>If TOKEN_TEXT = YES then NER(TOKEN_TEXT)</code></li>
<li><code>If NER(TOKEN_TEXT) then CHECK_PATTERNS(TOKEN_TEXT)</code></li>
<li><code>If ANY(TOKEN in TOKEN_TEXT) starts with ANY(“Bank of”) or ends with ANY(“Bank”, “Credit Union”) then SUSPICIOUS ENT = YES</code></li>
<li><code>If ANY(TOKEN in TOKEN_TEXT) = URL, CHECK_PATTERNS(URL)</code></li>
<li><code>If ANY(TOKEN in URL) starts with ANY(“Bank of”) or ends with ANY(“Bank”, “Credit Union”) then SUSPICIOUS LINK = YES</code></li>
</ol>
</details>
<h4>Part 3 - Sentiment Analysis for Suspicious Messages</h4>
<p><strong>Task: </strong>Assume for this part we are using a pre-trained sentiment analyzer, but we want to add special weights for the terms <strong>“URGENT” (-0.5)</strong> and <strong style="font-size: 100%; color: var(--ic-brand-font-color-dark); font-family: inherit;">“CLICK HERE” (-0.5).</strong></p>
<p><strong style="font-size: 100%; color: var(--ic-brand-font-color-dark); font-family: inherit;"><em><strong>Order each of the steps (A-C) in the correct order to accomplish the task.</strong></em></strong></p>
<ol style="list-style-type: upper-alpha;">
<li><code>If ANY(TOKEN in TOKEN_TEXT) = “URGENT” or “CLICK HERE” then ADJUSTED_SENTIMENT = SENTIMENT - 0.5</code></li>
<li><code>If TOKEN_TEXT = YES then ANALYZE_SENTIMENT(TOKEN_TEXT)</code></li>
<li><code>If ANALYZE_SENTIMENT(TOKEN_TEXT) then CHECK_TERMS(TOKEN_TEXT)</code><strong style="font-size: 100%; color: var(--ic-brand-font-color-dark); font-family: inherit;"><em><strong></strong></em></strong></li>
</ol>
<details style="margin-bottom: 2.5rem;">
<summary style="display: inline-block; background: #394a58; border: 1px solid #8A8B99; padding: 0.5rem 0.75rem; cursor: pointer;"><span style="color: #ffffff;">Select for Part 3 </span></summary>
<ol style="list-style-type: decimal;">
<li><code>If TOKEN_TEXT = YES then ANALYZE_SENTIMENT(TOKEN_TEXT)</code></li>
<li><code>If ANALYZE_SENTIMENT(TOKEN_TEXT) then CHECK_TERMS(TOKEN_TEXT)</code></li>
<li><code>If ANY(TOKEN in TOKEN_TEXT) = “URGENT” or “CLICK HERE” then ADJUSTED_SENTIMENT = SENTIMENT - 0.5</code></li>
</ol>
</details>
<h4>Part 4 - HAM OR PHISH?&nbsp;</h4>
<p><strong>Task: Sort the emails based on if they exhibit Flags 1, 2, or 3 (PHISH) or no flags (HAM).</strong></p>
<strong style="font-size: 100%; color: var(--ic-brand-font-color-dark); font-family: inherit;"><em><strong>Order each of the steps (A-D) in the correct order to accomplish the task</strong></em></strong>
<ol style="list-style-type: upper-alpha;">
<li><code>ELSE then HAM</code></li>
<li><code>If SUSPICIOUS ENT = YES then PHISH</code></li>
<li><code>If SUSPICIOUS LINK = YES then PHISH</code></li>
<li><code>If ADJUSTED_SENTIMENT &gt; .05 then PHISH</code></li>
</ol>
<details style="margin-bottom: 2.5rem;">
<summary style="display: inline-block; background: #394a58; border: 1px solid #8A8B99; padding: 0.5rem 0.75rem; cursor: pointer;"><span style="color: #ffffff;">Select for Part 4 </span></summary>
<ol style="list-style-type: decimal;">
<li><code>If SUSPICIOUS ENT = YES then PHISH</code></li>
<li><code>If SUSPICIOUS LINK = YES then PHISH</code></li>
<li><code>If ADJUSTED_SENTIMENT &gt; .05 then PHISH</code></li>
<li><code>ELSE then HAM</code></li>
</ol>
<p><strong><em>Based on our rules, the order of 1, 2, and 3 are interchangeable.&nbsp;</em></strong></p>
</details></li>
</ol>
<div id="fragment-9" style="overflow: auto:;">
<h3>Summary</h3>
<p>In this exercise, you went in-depth in your understanding of email filtering and how language patterns can be used as part of a multi-approach system to detect phishing emails and other suspicious activity. You had an opportunity to identify the correct order of steps for executing a simplified email classifier using natural language processing techniques like sentiment analysis and named entity recognition.&nbsp;</p>
<p>Throughout this task, you may have noticed that it can take quite a few lines of code to execute a very simple set of rules. This observation is structured to help you appreciate that while rules are an indispensable part of pattern recognition in threat detection, that machine learning techniques are necessary to handle the increasingly complex patterns that suggest suspicious activity.&nbsp;</p>
</div>
</div>
</div>