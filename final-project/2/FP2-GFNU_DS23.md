### SF-DAT-23 | Final Project, Part 2: Project Design Writeup and Approval Template

Follow this as a guide to completing the project design writeup. The questions for each section are merely there to suggest what the baseline should cover; be sure to use detail as it will make the project much easier to approach as the class moves on.

### Project Problem and Hypothesis

- What's the project about? What problem are you solving?

The project is to attempt to determine the best possible lending portfolio for maximum return on Lending Club.

Lending Club is one of the most popular online P2P platform that offer unconventional financial opportunity for borrowers with a low-to-high 'grade' credit score. These borrowers can request for a quick lump sum of money without the hassles of going through approvals from various traditional banking institutions provided that they opt-in to share their 'background' information, which may or may not be verifiable by LC. Based on the respective 'grade', LC determines the interest rate to which lenders will receive when borrowers pay back their dues. 

Building a portfolio on Lending Club can be a tedious job; lenders may need to spend some time to read each borrowers' (short-to-long) stories, background information, and assess the likelihood of borrowers defaulting. Lenders may also succumb to the more desirable 'A' and 'B' less than 'C','D', or 'E' due to the higher risk of 'these' grade borrowers defaulting. There are more nuances that are not mentioned, but I am trying to save lenders' time from having to go through the various nuances, and predict the likely outcome for building a better than regular portfolio to maximize investment returns with hopes to minimize defaults.



- Where does this seem to reside as a machine learning problem? Are you predicting some continuous number, or predicting a binary value?

There are too many variables to look into prior to dumping the data for learning. I can see myself using too many/less variables to make a sound prediction; there will always be outliers that may influence learning, and missing values that are unknown.

I am predicting a binary value for each observation in the dataset.



- What kind of impact do you think it could have?
I believe it may increase the likelihood for lenders to be less reserving to grade 'C' and below, which in return increase chances for low-grade credit score borrowers to also have a chance for financial opportunity as their counterparts.



- What do you think will have the most impact in predicting the value you are interested in solving for?
Lenders may receive higher interest rates if we can predict the likelihood of low-grade credit score borrowers not defaulting. In return, everyone wins: lenders get high interest returns, and borrowers are given a second(?) chance to rebuild their financial history.



### Datasets

- Description of data set available, at the field level.  (see table)
The dataset contains complete loan data for all loans issued through the 2007-2015, including the current loan status (Current, Late, Fully Paid, etc.) and latest payment information. The file containing loan data through the "present" contains complete loan data for all loans issued through the previous completed calendar quarter.

'''
Index([u'id', u'member_id', u'loan_amnt', u'funded_amnt', u'funded_amnt_inv',
       u'term', u'int_rate', u'installment', u'grade', u'sub_grade',
       u'emp_title', u'emp_length', u'home_ownership', u'annual_inc',
       u'verification_status', u'issue_d', u'loan_status', u'pymnt_plan',
       u'url', u'desc', u'purpose', u'title', u'zip_code', u'addr_state',
       u'dti', u'delinq_2yrs', u'earliest_cr_line', u'inq_last_6mths',
       u'mths_since_last_delinq', u'mths_since_last_record', u'open_acc',
       u'pub_rec', u'revol_bal', u'revol_util', u'total_acc',
       u'initial_list_status', u'out_prncp', u'out_prncp_inv', u'total_pymnt',
       u'total_pymnt_inv', u'total_rec_prncp', u'total_rec_int',
       u'total_rec_late_fee', u'recoveries', u'collection_recovery_fee',
       u'last_pymnt_d', u'last_pymnt_amnt', u'next_pymnt_d',
       u'last_credit_pull_d', u'collections_12_mths_ex_med',
       u'mths_since_last_major_derog', u'policy_code', u'application_type',
       u'annual_inc_joint', u'dti_joint', u'verification_status_joint',
       u'acc_now_delinq', u'tot_coll_amt', u'tot_cur_bal', u'open_acc_6m',
       u'open_il_6m', u'open_il_12m', u'open_il_24m', u'mths_since_rcnt_il',
       u'total_bal_il', u'il_util', u'open_rv_12m', u'open_rv_24m',
       u'max_bal_bc', u'all_util', u'total_rev_hi_lim', u'inq_fi',
       u'total_cu_tl', u'inq_last_12m'],
      dtype='object')
'''
loan_amnt - continuous (in thousands)
funded_amnt - continuous  (in thousands)
term - categorical (in months)
grade - categorical (A-E, with subgrade 1-4 respectively)
int_rate - continuous (floats, 2)



- If from an API, include a sample return.  (this is usually included in API documentation!) (if doing this in markdown, use the JavaScript code tag)
N/A

### Domain knowledge

- What experience do you already have around this area?
I am currently and somewhat actively investing and helping people around the world through Lending Club; am somewhat new in the field, but really interested in getting in depth knowledge, so taking this opportunity to learn domain knowledge and data science altogether.



- Does it relate or help inform the project in any way?
yes, it's related to what I am hoping to achieve: gaining maximum return for my investments, and at the same time hoping to confirm my hypothesis from my finding to further help those with low-grade credit score. 



- What other research efforts exist?
 - http://www.lendingmemo.com/lending-club-strategy/
 I read through some of the tips to increasing returns, but a lot of it is based on strategies that excludes borrower's error such as forgetting to pay monthly, other causes for defaults, ignoring borrower's stories and only looking at primarily the grade/subgrade for each note (borrower). I am going to try to incorporate these 'human' nuances into the prediction (unsure how yet, and I might be overhyping).
 
 

### Project Concerns

- What questions do you have about your project?  What are you not sure you quite yet understand?  (The more honest you are about this, the easier your instructors can help)
I have a goal, but am unsure of whether or not I will achieve it by this dataset alone. I looked into the dataset and a lot of information provided are nulls, and my concern is that I just don't have enough observations and variables to work with to predict anything.



- What are the assumptions and caveats to the problem?
    - What data do you not have access to but wish you had?
        - the most up-to-date data with users who have yet to pay in full so I can try to predict using the training data I currently have?
        
    - What is already implied about the observations in your data set?  For example, if your primary data set is twitter data, it may not be representative of the whole sample.  (say, predicting who would win an election)
        - The dataset may not have all the information that is provided on the site due to privacy reason, and this may skew my findings.
        
- What are the risks to the project?
    - What's the cost of your model being wrong?  (What's the benefit of your model being right?)
        - The cost of my model being wrong is investing in the wrong note (borrower) and have it defaulted after a certain period of time (unknown). When borrowers finally get their money, it will take some time for the return to finally see result, and at this point a lot of time have been wasted.
        - The cost of my model being right is investing in the "right" note, and will eventually minimize defaults, and gain maximum returns for myself and whoever else is interested.
        
    - Is any of the data incorrect? Could it be incorrect?
        - My guess is that some of the data could be incorrect because borrowers may falsify data that I have no control over? However, this data alone should not be incorrect because it's provided by LC in connection with Kaggle, so no one scraped the data or edit it prior to uploading the dataset.

### Outcomes

- What do you expect the output to look like?
    - This is where I might need help/guidance in trying to put my thoughts together so I can get an acceptable output...
- What does your target audience expect the output to look like?
    - The expected output should help my targetted audience figure out which note that is most likely to not default and with the highest return, which can be easily combined into a portfolio.
- What gain do you expect from your most important feature on its own?
    - Moral satisfaction knowing that you're helping people who would have otherwise been rejected for a loan due to low credit score, etc., as well as financial satisfaction because you're getting the most out of your investment (in people).  
- How complicated does your model have to be?
    - ...
- How successful does your project have to be in order to be considered a "success"?
    - The average return is approximately 7-9%, I am hoping that with my project, it can be higher than 9% -- this is what I will consider to be a success.
- What will you do if the project is a bust (this happens! but it shouldn't here)?
    - Try again, rebuild/fix the model?

