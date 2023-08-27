# Lab 7

We now start with Lab 7. This lab will explore machine Learning capabilities available in Elastic.

We will be using the same Elastic Cloud instance provisioned earlier.

---
## Single and Multi-Metric Jobs, Forecasting

In this lab, we will be performing the following:
- Set up a single metric job
- Perform forecasting
- Set up a multi-metric job

## A - Set Up a Single Metric Job

1. Click on the “Machine Learning” link in the Analytics section on the left side of Kibana.

![](https://lh3.googleusercontent.com/lQkZvEfzqja3vXVjqhAINuWZPFJLgNoePEhLTYTzLy6KqYU4Hrz818RPsbr0M1vn_EMHruayqhsFCrnFFtLZnN9oyxn7n2HpeoM8A1HTc-H-jhUYlXDPROZUiUdaKYzvM7ENhF2zRioumodMGgkIJQ)

And navigate to the Anomaly Detection section.

2. Click on the “**Create Job**” link to set up your first Machine Learning job!![](https://lh4.googleusercontent.com/jddw8mIKqIQ8VEJX_91XyyC1M285fxwdU2AEKfMdwpJ4fb8cDYTHTVSioAAezXFe3HY-um5GedVaQbnDFkBNAAh1Sk1bNEbf51oZfYs24q6945bqQBNTUsToAEAmVY4kUWSyrLKDi9gE5LJyuvaKrA)

<!---->

3. Select “kibana\_sample\_data\_logs” index.

\
![](https://lh6.googleusercontent.com/sv-wfylnk8foES720V8md_DhyqqOiYIlhVK_l4tBuXbbZkoVIQEjg_iUtA87--2RnP5PSq2IKD15xHN4KCeksk4vAsRY8bnk9yW9riOF0_X8XXzgMh3hEWbLZ5qbA01orc6FbfGmOven5yjOW646Lw)

4. Select the link to create a “**Single metric**” job

![](https://lh4.googleusercontent.com/2P6lfhno8Wp9JPhO5AHQOyx3QzQ0iRzFSrahe0B8wuXD3mXsa_WFWN5pIG58G10brmQ_kfIYMA9kUFTFLBNerHBWFBgTf2pd1YN2X_dJKMklwcGJopDQvZ3xXQZhfetHd9L4qKmMmX2yHBB1K2O0FA)

5. Change the end date in the Time range selector until you have 8 weeks of data, which is the full data set. This date will be some time in the future since this is sample data.

![](https://lh4.googleusercontent.com/cfUuMHIBHOiU2CPFS5lUkZIUge06X5Wuu1c94cdq4l2XxPDn0YKc0qbldAaoLH4oI55pCJIzB19X-xtjpP_QSk9apHtUmdKLYDUjlZwvTIyZIdeL8VrwtXmTeDD6wfaTMaMj9ildbwOE3Eq22_4ESA)

Please note that your end date will not necessarily be December 31st.

6. Then click on “**Next**”

<!---->

7. Select “**low\_count**” function

\
![](https://lh5.googleusercontent.com/beyyXCfUF9IthkhYJCIcWiI9IJZYly5yC25ir5XorkT6IRUrkvbIAdFwnQzpZsifKzomT-7OiuwKb6Dl8dJWm_cI4ZZfY9Y4zivtuU3IqZ2Lrb_vzoXQjU6gwc68YfGK1IxFyn4EErPSOiOR1_FD4Q)

8. Enter 1h for the bucket span and click on “**Next**”

\
![](https://lh6.googleusercontent.com/13HUdTgxtsOBS7GPRBZLkMx_1mjTgW7nZB8ryQAXeKMomvBUzOhz60WKN6NSQqbOAkMHk_xhXjE97NVL-5KYNH_rh61qwlSm89tWV7E0ggX03LYese8Wi0IQMPjazWPi6uxYEW1cWHI94RiQJK7fQQ)

9. Enter “lab1a\_low\_web\_traffic” as the Job ID, and “mylabs” as the Group name, then click on the “**Next**” button

\
![](https://lh4.googleusercontent.com/0Nj-edPaYOADbp586Z5wf62J9p6Ub0IgS4zvGpc9KzpX00mBVPcZ8MmRE9lhMs4kCCRJRS4ZN1BA-OxekGE83T8Okk6Fbyi_HFF8xWXY99_zTZtyuj82MtnXQVFhB7539O2DnQyKAWVVYeEL-U-CeQ)

10. The data validation step should pass without problems. Click on the “**Next**” step to proceed.

<!---->

11. Review the job configuration, and click on the “**Create Job**” button to start the ML job.

![](https://lh5.googleusercontent.com/EG8I1eTWzhdDWyb7NBtduhJ6sQqgeQwmb04j-WJqC3Jyyg_7bzy9LIxPcLT7_lPU-ecJFrliBMbTbWTYypPMUbto_OfS5z-_XXAU2spkJEj6FjqMsi1XqPK16NeFDM9Y43JuSmqG0apNQ4_tRYv_gg)

The job should take seconds to complete. Once done, please click on the “**View results**” button to view the results:

\
![](https://lh6.googleusercontent.com/WUA0hWohsRxT655296GdByv0k68Itc1hSa-W9rbjNL5ZGJIsPAc69R_82rTQxJvkOIPoNtpd1pZe0BubR39PrAc6pfAjEZUUOS6T30YI7Kw5noW9liT1-yH4l2pckca6wlx5dQFarJysKWyf16qOCg)

12. This is how the results would look like:

\
![](https://lh3.googleusercontent.com/4-OTpHJUda3XQGed178M2v5-X0Q15V9Fq_E_63Hneqw7TgcRsolxjvDuHOitIcLifYlvz3wN4KT87GBBWtEZG7NltpdhgsuBu_Bzq_-SqqYOeOBw1wr6rOgaK6kGdAjFIZSRt8aAXxj74RQgeAecDQ)

13. You can drag the “timeline” bar at the bottom to the beginning of the time period, to see how ML “built” the “model” (after about 3 cycles at the beginning of the timeframe)

![](https://lh6.googleusercontent.com/DzqoRV1mU1_DEmbpqu4D8bLZGVtQbsNIbcNsOoEosbs9scoGv_ymIHeOVIOXN1otrZzWcweW2cGgaGPMSRrHU6MJz-IQUVGUb2ge8cYK6hOvWz8TvRfR7ends8S6i-_UeWjBIY9LPthZQHKrpRJliA)

14. Next, drag the timeline to the area with a “red” line to check out the anomaly found:

\
![](https://lh4.googleusercontent.com/awof3Kv4lNUJqcx79aaBFM14Qs8woGrIqdwV1AdLm18u_Vkthki2V5vhnMltj2SynjXI5OdME1bny5hzX31VriBWKERezrHDhvQa7t0CA24CuM_rUhQqRytkNfuEb0KZxkDSZdG2-JWmCYG9R2VaBA)

Note that detailed information of the anomaly can be found in the anomalies at the bottom of the page. The anomaly was given a severity of 95. The expected count according to the model (for that time period) was 28.3, however the actual count was 0, hence the high severity.

15. Note also that:

- The drop in traffic was given critical severity score
- Spikes in traffic on the other hand were not anomalous, given that we were looking only for anomalies on the low side (“low count" function)


##

## C - Run a Multi-Metric Job

1. Click on the “**Anomaly Detection**” link at the top of the page in Kibana.

![](https://lh5.googleusercontent.com/c8R4nO2I2y7U72mi6Vl3NghfZnAImSxf_UcXgXl9Rhc7t45rzlMyso_YQddDKBEXXISH6y9LkROFkNZ6dnNs7EmDF_GbaExwm6Ox5ukaLObSxsl_65t_wVogQ0XRe5zyN8F9yWMLMbrZBBQ5AkNhoQ)

2. Click on the link to “**Create job**”

\
![](https://lh3.googleusercontent.com/5YjvGDeL_4_WVZXwHyL8PKKgjNX0rrwKPloFumhqP8CEHcdBe7sikcA5kCZjq7FC7ASRY6mLFto1u9Zzk9OY9rAJBGbz9IMQ17iulkza-BwXa5hnWTkN1cUSU9dzRd5BeCz6s6xBZd8gRgqStOq_MQ)

3. As before, select the “kibana\_sample\_data\_logs” index.

\
![](https://lh6.googleusercontent.com/sv-wfylnk8foES720V8md_DhyqqOiYIlhVK_l4tBuXbbZkoVIQEjg_iUtA87--2RnP5PSq2IKD15xHN4KCeksk4vAsRY8bnk9yW9riOF0_X8XXzgMh3hEWbLZ5qbA01orc6FbfGmOven5yjOW646Lw)

4. This time, select the link to create a “**Multi metric**” job

![](https://lh4.googleusercontent.com/b1HAk304GeeFApEyWP3yjYNHLuOCSSUioSQKM_auABe1grlCbHJYUCIShfKu6fOIf7AqrQjApiP_IbpyMC5Nrs31Trwc-AXaYw9TvDmm-gqImP1CJmILgtOj_74k3mupEvxl8uE9xsGwr8x7ZUqsKQ)

5. The full dataset should still be selected. Click on “**Next**”

\
![](https://lh5.googleusercontent.com/V9bCvMSrnkSY1rNYNGa14HK7NlMYe9EYtiqWeML0i0Zo-O15lA_krLVqVFDQhPcuYxNK4i5NtOQ2Jb-xmZ4EiMjCwrQx2C-klnRQ2PBgrNT7bpHYoo3D0F0cQVAAOyoUHbev2ZTVkk-sLsGxsjA1jQ)

6. Select "**count(Event rate)**” function

![](https://lh6.googleusercontent.com/10XPrYZhrIvOcJxJ2jEBlSFo1Ax9fivLw3im4rkhSxW4FtIzvVlT6tSliDIjHu97N9IDCg-gKAUrY3fIRhCNEEJgmG2lAEW1cN3dLByEMcsXzTvzZGGsfrXKmQIGWO2eYVmMK9WgTHfyvHxPeprFVQ)

7. Under “**Split Field**”, split the data on **response.keyword** (the HTTP status code)

\
![](https://lh5.googleusercontent.com/mIL9qT-MsqWsh208y8wqvV8p-iLevRPZGp9RUXpGrcGjXKh5BJBNA1pKg2LTVylhq6KNCWxtMTA1qVNvt4K8t9TRJCbId5vpceAmPGEsmJ0RkRbRv5C_36QufNp8iq7Y6IhS5DCVFrVIrH25vv0uUA)

8. Under Influencers, add "**clientip**" as an additional Key Field 

![](https://lh6.googleusercontent.com/VpqR_9KWeCJSMQegkKdlemyAOZ0lLopsZz8-tUTVe0nURq7o4w86fj7k6fmHyA77m8T_QDcFolDI395Da-NAGsREyJp0jl4VSlHrvMWCEUEeSXA5v1PJKbO4fm5tlj10_ahtvRuFhdWJtVt_TBkHeg)

9. Enter 1h for the bucket span and click on “**Next**”![](https://lh6.googleusercontent.com/L4lMBRbjB5g6x1HqQJZ8HssiLI2g9DJCxKGQGOOpKoFWOakeNijuuiqeENtmNtaif-KVTWNZzcVrKovYCMmYETmJaloAtEi0XxWzYNafeQpBo0HqYWAJqsJwk5EAzcLsPB6SgqXnJ2wmsk6MYK2Qzg)

<!---->

10. Name your job as "lab1c\_web\_traffic\_per\_response\_code" and place it under “mylabs” group. Then click “Next”

![](https://lh5.googleusercontent.com/XBfEArDMNVEoiODPDBLjL4Y_iSlzkdOEVGQipROdxKVsav-3GqjV98XZu48afrD8EXvc8u852cmJB3Dv5cBRA3qiGIOwP9_ueDCVuIkwXL5z8icsHgYuPvbvCBNxrEuoViv6-4cyYr9z8T1M_6Sczw)

11. The job should pass through the validation. Click Next.

\
![](https://lh6.googleusercontent.com/4FsX6f3u3vPNPKWwNbOKZNSKB1uUbGcgrV_G8p31iKLSGxyk70NsPf_ATrihir7djx4nZ6d_ZXJ1mUb3lj-tgt3X5dUPwORDwfXRe-CuoSkyUSOlF4deoJKrLzD92XORa3qENSTA3l_iwZoJN-NEaQ)

12. Review the job settings and click on “**Create Job**” to start the ML job

![](https://lh3.googleusercontent.com/8-PsUNGj5X7r7glKooyuEAXMoVnozohR417rOXgRrdZ779tEDH140DabOmJjy1aU0UO-tE0AOKV5U9nFWdboFudZSJJPetkf3bCe8nttcbGeTOIKZybDIsKNbFQneCdhUWzVwqY-FMve8F3yYQP5ng)

13. After the job has completed, click on the “**View Results**” link to drill down to the results

\
![](https://lh3.googleusercontent.com/mdBnPEPo8I5334SgYM7jSUWKddFF655cFFPEj7EjLfbvl5BnkoVW0M1Gw2v5zZ9hJMe48aeWybeLgyYlWkSd0Tf5_gQuAt1bfy9eQA9XFIiCWfnXRhRyAA-h2LpQ-6bydE6bL04xzmbGIJ9GZQKRZA)

14. At a glance, we can tell that there were anomalies associated with response codes **404** and **200** over the period, and that the anomaly related to 404 seems to be caused by (influenced by) ip address: **30.156.16.164** 

![](https://lh3.googleusercontent.com/dO7UgyHNYmQ8Ju9IqSN6MUQarLwJ4JT_v3jYBPSIitjHMdwYXpeBpOBOWq4OneSZj6D0NdOHoeIVdyRDT6M4tBlYs9QWDMZI3rWD7fSpb1W9bDE7-Bm4-TXmxq94uUw50JUcGNPrpXD4etdRKFNagQ)

15. Click on the red square for response code 404 to drill down further:

\
![](https://lh5.googleusercontent.com/L5mYmh6Dh-bwe20ezIemkzR0bfA4VTg1oOyWS_Txmn2BSY7C-tIj1f4bh8joVBAVXjH5bna7Dgqcv8oDIhWmMsUQY5kngfCogINUfvdPgD76eQMsZtk3lJu9Fg_tDuY49GUkES37pm08UmtaQmOIZA)


## D - Add a custom URL to the Multi-Metric Job

1. Click on Anomaly Detection to access to the list of ML Jobs, “**Edit Job**” for “lab1c\_web\_traffic\_per\_response\_code”

\
![](https://lh4.googleusercontent.com/YeV-IXqIX5RtIKc2seq6zZfTis2lLe2yVnDaeSShk18AwvsZCmo_cJPLxt3rRq86hYQ-tW3KwarcaWf2iy61lb8IpWo3Rb0Qp4fninVQzfhnUC49-Xe0sBeNyDPuWCUKkti6TWcqz1Sz2iEMNFvgYA)

2. Click on the “Custom URL” tab and “Add custom URL”

\
![](https://lh5.googleusercontent.com/Bah7ffnqw3r-i16IorMhYD0qfmOK_Dh2AJxfouQfFy48IvuQK9LQXW0RfF9zW1g3wpmEwTJGL-Ijt5LPWWz2DCYMxkScR4DhDQSWM2bdb1-H3DIkWrX2kBNFy6eZ-64TSUeJ809mpjdelVhorbhGjA)

3. Enter the following details:

   1. Label : “raw data”
   2. Link to : “Discover”
   3. Index Pattern : “kibana\_sample\_data\_logs”
   4. Query entities : “clientip”

Click on the “**Add**” button ![](https://lh6.googleusercontent.com/-YPcwKh4_5qGtiA_K2i_RFLYrN1FMhHsI8UabR9l53SjzdDASgCJ3iNBeM1vi57Ua1kVcCJX95DBiJRbt5PIzFYQKLOtq7vVKCjEV08vMq5JDw7iEFpN2MZiXKpLcIP1G0PJ4C_FQkBRceVn3MFvRA)

4. Remember to click on the “Save” button

\
![](https://lh5.googleusercontent.com/BXs6ULhmqtwyCVWBsgiwBk6zT9eZmKPfGNbHIpug54g7nqNhVJYQxZ6-FG-LDyJPRhobgImqCwZ0AvwzuDHnRZvLZa9nFo7vyA6aGNVL21D4Ca3kfjZH2-3Wz1JpmcR-eRVk099QYnmt6nmJCsINZA)

5. Now, let’s go back to the previous results: Click on the Anomaly Explorer link for the lab1c job:

\
![](https://lh4.googleusercontent.com/BD4tuWhIQb6HgA-VuWTiA2GXIJzcMfHRhT6fx7mDo2Rb2AogYC41BOMjYfkyiiN3hSdRJCU4GzUcxAq4Eem0aDo2jXLYiYxgTnaH_jzThMVaaf0AHjhuKNI7czRaRJZUqi5oNEuyglFgfuWO20U3Jw)

6. Click on the red box again for 404. Click on the “Actions” icon at the top right-hand corner and click on the “raw data” link:

\
![](https://lh6.googleusercontent.com/ehMyufp1sEa-6kQD6sSSB4N9rqjsEQquu7gi47Q4fqkGWxIJAhdEirHFVUyREqcEV297oJ9hMrqDtJShU4nunyX0PbxLrzNoCBj7yXvIn0S7e_HoUhf9DavFyVxrMaY_aEVCYLPqutAptjQamwjTYQ)

7. This brings us to the Discover page showing us all the relevant documents filtered by “clientip:"30.156.16.164"”

\
![](https://lh6.googleusercontent.com/Pu7hNo1WGCzL5yZQNbXC8RwObq4rZfPzzmauvAUOjq52aymmBupWReaKO-2wV8YzxbchqvnNmQZ3y29kfb5L3-TDOPgnKpYljUt_n7-iTGyw-YMvxT1L5XS0Gk7MGQLzHOGfdxVNA2Cm4bRvL4p96A)

8. A quick click on the “response” field on the left would show us that all the 100 requests sent by this clientip encountered the 404 response code:
9. You can also click on the “URL” field to take a quick look at the URLs in question:![](https://lh4.googleusercontent.com/9C66NMl7GJjqJyEJ1FdU-krXqJ6syiMY4WPoYLMLAo12fm3vn2IEvoSl39Mbr7bl20wOgVeC0UmCTrbEmpuB98NHICRmLGdk9FJK7H56dFyRHBHApOKtfOkGDCT9WuXz0GnO5VSawT6r5LQWbKJ34Q)

![](https://lh5.googleusercontent.com/URWUfIgshZoJKUv5zo-HIiAMsyj69YlEPkG_nmMrFvWL91beqHH0sxwpTIXl9odmexT2mrSvwXCATIiw48umnd42cN_q8ayOgjdcHQHdI2kbZa-l-_YUgIMEe_jScARQa6N5iI1oVAa5zlDBW3O0HQ)


## E - Add Alert notifications to ML Job

1. Click on Anomaly Detection to access to the list of ML Jobs, “**Start datafeed**” for “lab1a\_low\_web\_traffic”

\
![](https://lh3.googleusercontent.com/1faz-d8stT3EQHozS9ocLBZWZBCnlpnfNqjetFVsxfj2X7U7gLAEUxsYxLQFafF65tbW0OOYdsxwmYeEUxinERsB9T43ziU8zDZdWQRFNXiDJQW35zhJ0HH1ssgTqvW3tp4hr0pGlLSjxPrZMXbjTQ)

2. In the new pop-up window select the Search start time, from when do you like to start the data-feed, select the first option “**continue from ....**”. Select end time - “No end time (Real-time search)”.\
   Check the **“Create alert rule after datafeed has started”**, then **“Start”**

![](https://lh3.googleusercontent.com/fXMsoQpcxcMZCrdNzQ_DOBg92pxn8ar06aha74n7UC_qKlPjE3uonHi8X_3zr5NEy1o6-MVHkqgH5oHtuEhJk3yqk1sQiQ4RxJyxHCsdpkX4U3pkD803cIVpldzjYixtDbPAFLblbacVgavblzNe5Q)

3. A new section will open on the right side, showing the configuration of the **“Create rule”**:

   1. Name: low\_web\_traffic

   2. Check every: 120m 

   3. Severity: 75

   4. Select a connector type

      1. Select Email

   5. Provide an email in the To box

   6. Provide a sample Subject

   7. Click “**Save**”

![](https://lh4.googleusercontent.com/toPdGO-Ou61zR-7YkqTyALA7kR5qCzFl0UXujk65ujg5Djb3jVMTChOk-3U5p3zhtgaC8bvy2VYk9f3x0G8LVzpQunp5Eby1DOKn-3wT_5zp_hgim7uZMMMdmcLHrwns05lZVnA8D6PSW_TUR9-xWg)

4. Now in the Anomaly Detection Jobs list you will notice that the “lab1a\_low\_web\_traffic”, the Job state changed into “**opened**” and the datafeed state is “**started**”. From now on until you will stop the datafeed the ML job will collect the new data and notify you, based on the threshold settings of the Watcher.

\
![](https://lh3.googleusercontent.com/YqA7XeLFv4iEP9_BW9qD6sYegovod0q0FPoFH4iy4pn2wSUs9ifgb_4LVZzHxXn1Ovz4ytLGmIxXuMZYNrVFlrJlQWQtf-pnsNWh5XJFEcdlR144xQS32CyocwTZWpjINKlSm1nJEvHJ7S4HIOiYzw)


## B - Run a Forecast

1. Continuing on the ML Single Metric Job Results Page, note that there is a “Forecast” button at the top right hand side. Click on the button.

\
![](https://lh5.googleusercontent.com/At6ju3tzsEjbQA1jRukmuVe8VmJKyDiTOtVrhg7VykiiY4oUOXXczdNgj09lYfX05A87lzNy35u7lAQBmKdd13hAdg-rR6U6McN6E9vkmAhdLzIcL3tQP0cleA6x9PXlss_fDp-gy84Q0p3ykAIkuw)

2. Enter the duration which you would like the forecasting to be calculated for and click on the “Run” button:

\
![](https://lh4.googleusercontent.com/yKE0zQ66Ol2uO6H2x0EgKHpa9Lnj2QGYkFM_ZjTiU5zzp0DqYrusglZ1_NqUdk4VYBaf1FS9LZYnwbNreBZJjWUh-R8MCBEE87cXQfxR5L1kwRpKepd7V3dKGl3nPC5vuwoKP4efVbiyGB9nHEoPgw)

3. The forecasted results are in Yellow lines:

\
![](https://lh6.googleusercontent.com/iGfjXgFlKa4w29mOxl85pp4fovMPaOEUgd09PF28jNSa8N-KbmN6A8MRO7HCmT0nGWuPg8jIyWG7WjJhgCP08a19CMnMcM6gGRPAS1aLbdQmr0qWb3FRmsTfx0Xy6fKBW4QDANXgkh4jQPUpNwYO6w)

---

# Lab 2 - Log Categorization - Detect Unusual Log Entries

In this lab, we will be performing the following:

1. Import a sample log file into Kibana
2. Use Log Categorization to find unusual log entries**

### A - Import Sample Log Data into Kibana

1. Download the sample log file from:
   [IT logs sample](./it_ops_app_logs.json)

2. Go to Kibana > Machine Learning > Data Visualiser. Click on the “Select file” link![](https://lh6.googleusercontent.com/HpkIt9ZDYXszS-yOf5dk7EwEdumLovvu_FtNZYa_re_iIdG1nS3JZrXexvh3DbJDobPn6v-bYruooXM6zJ_LmVfwIrQhpADxrnE8VUn-TUd-KZLVndbaZI7i5fZ057uQ0xcRGUFebdq1tXrL7iIRbg)
3. Upload the “it\_ops\_app\_logs.json” file from Step 1 above.
4. Accept the default mapping and click on the “Import” button at the bottom![](https://lh4.googleusercontent.com/WGkYxVGMnzVWCmXenUlRGbTVz-D7IMlxJvF4ikRMHAOht5cCnHeQxXZHFUl1srO5q_RqRQzyKNsL6lweX_HBAC8HcqzPxrTSh2YZDu0otzHDI-0tvdfPtz8mXdNkn_dukahQFRnQjeM-NNfc1SStlw)
5. Name the index “lab2a\_it\_logs” and click on the “Import” button ![](https://lh6.googleusercontent.com/BQAcYrjgmm9SsmwgqXLRhMqgJPIcgNXaNZWuidKZJ_m4T06NIuK1NoQi1A7H6pa7u4CpWfwTHk4yI2OuFPuoydS8pegNkaVAMqJIMAo1QmqGkmK6aBZ4n6rRof43wNs1F7d8woqhLEN1JG4HAoXvKA)
6. Once the import is done, click on the link to “View index in discover” (In the next steps we will also be creating a new ML job for this index)_To speed things up, you might want to right-click on the links and open up different tabs for “Discover” and “ML”_ ![](https://lh5.googleusercontent.com/_1Ozb-ywsC7PlZHouFGL0rsW3NVVVpmHe8yCrMuFdtelzsobuM7cLAcwMRRy7tBH51ytu4jD8t8A06TMOnosp3S3leLt0I8nilPjjBHtjqz5EclGX7kD7CZzuK70ljy98iWBnlx93d8iylZJVJ8QzQ)
7. In Discover, note how the raw data looks like. Note that the “message” and “message\_text” fields contain the log message entry![](https://lh5.googleusercontent.com/1cJopSpqoF3LujbuEMSn4JhcPiERtMQxX4KfQBMsSo-WLOnCsXosTkT3-UIaNPwuyzFVAL1zO59Gzarqwerk-rS3r3HilMP1NGRSSBNoJqzwKfUiPZwHXL94MSrIbUgr88Y094xkX0RF-5IDbnOLOw)
8. Click Anomaly Detection, and then Create Job button.
9. Now, let’s create a ML job using the index; **labs2a\_it\_logs**, to detect unusual log entries.Select the “Categorization” job link![](https://lh6.googleusercontent.com/sFz1pNyx6McZZeCp2MQXIaUFkeeQT0DZhQjrQUJEPwNZ5Fd9zuFUMa4S2rPl_FIafmZD2XzfzHXnE8RPGjxltKQSh-55Zb2mlkyK19WhkowfRo2xZTt7QoeTQHnZVLAT8UUJFlak0LFl8RGyIAtVkQ)
10. Click “Use full labs2a\_it\_logs data” and click “Next”
11. Enter message for Categorization field and click “Next”![](https://lh6.googleusercontent.com/NgVJn3viGW6gNPmEJoNuvAeDEkclvL6_8z3SQDduXeBsyJXReYiYJl6IPbD8787u_fRtX7LoAvmZmXTzIAsjACMCsH9uF4IzOvWA2zGTM6t0gwOxWDounawx5TW-Oz5KwRdUREfo81ivN7ELa7hCnA)
12. Name the job “lab2b\_unusual\_log\_entries”, place it in “mylabs” group and click “Next” ![](https://lh3.googleusercontent.com/j71i28hu5DjCYud513lKNz3bw7PtlGvCU8eOO-pKswuFL0tJM3oQoCY6-Yqtp5uGkGX47DDlcpuchx0BkuK0tNVEXNo6BmowA5Ym_rlfEEnuBKtiURpP_rjpZpL0aagPQdA-NYdujqFH8n6qoCdsRg)
13. Click “Next” to progress after Job Validation ![](https://lh4.googleusercontent.com/8zZ1JhYyU5P3OROQZyEfl71ZiOTBbVL6yZo0fdOIOCijBg_fyDCqjj7rUdgDmHx2E2eRiAxh68kzQSVmPw8eLtetpQMspkEOwL3VejYtebsN7h3Z6zijpCd8hKnmbB9IadyRfjXmjIYFbz68mHrFKA)
14. Review the final job configuration and click on “Create Job” to start the job![](https://lh4.googleusercontent.com/06Xx12mR4TkWEm5oJvJAE9ssgLBuEJjgbXstkLpuSvbHJW4SqdRUtcW35vxrdp8OP8Nk3ETZWTkSCUwIpNa7r-AHWIKKapvtqNmnQG6eRH0Ni4LpWbjx3eke4z_i9ApF-Spneo8VK_myN32YHRJxBw)
15. Click “View Results”
16. We can see that the ML job flagged out abnormal log entries![](https://lh4.googleusercontent.com/PCX7wrOv0aIwiiQwHUUEiZlXhZOgcjrohnBlV0Vvgq76Y_Z_CrZUULWWKNbe12CY9wO-dA1J0HDWVBTT_imj-tpbUzAJ8VNumMpzhdC7SPYbAD1h_pRDpXmQLVSqgRbwpNyGliZ5aeK6f9mPg7G-RA)Typically these categories of log messages only appear once in the time bucket (default 15 mins) but the count went up to 49 & 50 during that time period. Hence ML has flagged that out as an anomaly.

---

# Lab 3 - Population Analysis, Data Frame & Outlier Detection

In this lab, we will be performing the following on sample eCommerce data:

1. Set up a population analysis job to find unusual customers
2. Use Dataframe Transform to create a customer entity-centric index
3. Use Machine Learning’s Outlier Detection to find unusual customers


## A - Set Up a Population Analysis Job

1. Click on **Kibana > Machine Learning > “Anomaly Detection”** 
2. Click on the link to “**Create job**”

![](https://lh4.googleusercontent.com/q-gAVKYPlEcXvOoeO3zhp6wEFojb5jwzsSXIAVJNfDSqZUdGFPoleMTkNI8NdGDfeuftYIJ1m9QSTykuymeBUh63ppHbFJEX7V2BxwwPw7FVp0yZ4Pp9EHbppkUtNGF8iAFr49nmHeJE7cIzdWE2MQ)

3. Select the “kibana\_sample\_data\_ecommerce” index.

\
![](https://lh3.googleusercontent.com/Gb594oLm9z_wVyWEkzFk6mJZPtRoRM4h_yKvAO60VYiRip3-1F4bKAKnVYM3odZmLu2MqccKxVbW_bLlbUJh-iZs0Gx3wCePq0B9C49nR0GgP5Fw_G4aICjy0ddcIEokE9n6lt9lL8GxlhEOjyJeVg)

4. Click on the link to create a Population Analysis job

\
![](https://lh3.googleusercontent.com/dDtb7_DA2Rl6buCf2SqoME5Wu11hQPs4I8mYpOeh8SvYAZrwEX1VBvxCRNmek5LpNXxoWwkPElGPYph5tSqhXAgC4I5JU5x3NIM8RQM4it56A3k7XSKqrbSFZT4ART-K7nQBmqjD2HEVzMeZeOznWg)

5. Click on the “Use full kibana\_sample\_data\_ecommerce data” button, then click on “Next”

\
![](https://lh3.googleusercontent.com/sugXZd77F-v0vmoqzR6ZpXgTD7gG08f3gipKYoFb3JmHplrnMibxvhP62qbaIbJWZ5XiE6K8vGThS_5r4gNdQHnHyTUiNe0uLSBPcmOGtBtdYvsyDKyF0ZF7aBq_xL9rLd1uN42XLGmPPsO6QYhLsg)

6. Use "**customer\_full\_name.keyword**" as the Population field

Add Metric: use "**sum**" on the field "**taxful\_total\_price**"

![](https://lh4.googleusercontent.com/X9Tizvilq458FVXj2Y91PDd3wrafRHFRhqwOrVzxIpC6KC2-cxLejkuojn2al3mN024hOL6_1_RWK2739NVRZuMF8sq7D99-w97mLmsySRJI_ejUl9Dy9tA6HA3DQ5bjnyXdboFPMhkMZN3L9CCXEg)

7. Use 15m bucket span and click on “Next”

\
![](https://lh5.googleusercontent.com/-pJaTlAA4R7nuERYMzz6j3K-8mULgv3UNOJECp6xdspcexzdtAGPO4u3K8POzqThBcsfE4EtLqEnamASd02_cMc8DjAyBvnV9J8hxK5ndoGgVTCUnh3CoKhib8q5QpP6daf9_8LVJFFEuKfsMkRtyw)

8. Name the job "**\`**" and place it under “**mylabs**” group

\
![](https://lh5.googleusercontent.com/8dLmhwfex0nbuoltoHb_Iy7ciZh91eVsHS5S8KYTuHxnUtoBmE-b_l11NHyQyHtkOPBRFHSgON_nFGuKAm0suZCJA6DYpq-IFfWlCydpFUFqcuAY9gd0os-a8DnX7oMBio6oSAkl7eMYU8h6zAPNzw)

9. Click “Next” after passing the job validation

\
![](https://lh6.googleusercontent.com/CyBRp9N-58fcLDuc2niXnLv8UZYtW-HV_-2JrrsjqATrLbrmvpABgSNBlWXY2mHh9VRXpvtg_Q889bJlKi8DmB3wIbSBxbL7_dFp9U_GXWn1sgw10VVReo7gsKYI5FhL90F3Brrz9pYBa3x_tvD2fg)

10. Review the Job Settings and click on the “Create job” link to start the job

![](https://lh3.googleusercontent.com/Gvr8bmppcIlPZy4KV3d_RnVHuCs-8do-l5Ra8RgakZ0ENTweYXrlx-rIjKbKOeYqo6wCrU62CZ8vUwAtOtj49i_Z81cy_uRG3fOG0DjMw92lMdM7UU71og9X7RfzPa-xUsaKjtVUR-mUu2MOUsvujA)

11. Wait around half a minute while the job completes. Click on the “View Results” link to review the results![](https://lh4.googleusercontent.com/iur-2JcJ2J9CEAB7OwOGSBgYJKfCOYwPwif_799circqstIc1O-sQCjlevDeS4Fu4b1Y7sddX_vedS4HcWixm2okC2mlvoB4it_gdaDsK5jvH0jT06w-qpg5LiSQiZgfQ9dfBfBU78Tetu40wmVknQ)

<!---->

12. Customer "Wagdi Shaw" is the highest anomalous customer

\
![](https://lh5.googleusercontent.com/hkK-zd8ZO_kChXCY98iU7xGOq_Iy7ZiQaQeuQFEt5nmiakHXTT-zIfYrUYz2jr7Q3es8WJDXVgBjgwpnMBYBqeRZmpmHq8JQEUdV5qlFqJTLYV_WpnvWqWbVFcB1V7gSRhaWCujRLpGnrZUdYGBSkQ)

13. Explore Anomalous User - 

Click on red tile for user "Wagdi Shaw"

\
![](https://lh6.googleusercontent.com/-xJ6coFkhURU-BUZvU3b5Dw6Yc-05G4PRAo1vBlMxY3iO4SHEbVAl07QnM0kqR_H5ijdy0fqYNgJ4ATKrdNER8xVS9xKMFWdPQ9__pSZYXyiZ35Olv7hj4_AnbxtFsz89vMss4fz_7a6PRKf_Ev_VQ)

Note:

- Wagdi Shaw had a purchase of $2250, much more than the typical user purchase of $62.44
- (Optional) You could repeat the process of creating custom URL to raw data (as performed in Lab 1d) to see what Wagdi Shaw ordered


## B - Data Frame Transformation

**_Use Data Frame analysis on Sample e-commerce logs to find users that spend more money than others_**

Note: This is similar to the Population Analysis, except that this is not time-series oriented. In the Population demo, the oddest user ("Wagdi Shaw") was deemed anomalous because the order placed at a particular time was much bigger than the typical user. But, what if Wagdi Shaw had spread out their spending over many orders over a long period of time. We may still desire to know who our biggest spenders are, regardless of what they do on a moment by moment basis. Therefore, we need to summarize their behavior over all time (or a longer span of time)

1. Transform the Data - 

We need to Transform the data from the time-series domain to an entity-centric index. 

Click on **Kibana > Stack Management > Transforms > Create your first transform** \
or **Create a Transform** (it depends on your environment)

\
![](https://lh5.googleusercontent.com/xZb2YyIfrOCK8kTZZt2Z4ancEFNM689PD4CrcGfXPePksUAkUSyMUJQ_AxbzQpR4On4LZzcthXYfUmSPXppj7Y-DyktYYNMqAMGThbY-FJiJRrKs5Rprh6oCBqmjBYRq6IQcfS1uBnCC2b8B2Us5ug)\
![](https://lh6.googleusercontent.com/BwmTIWnU9-251YnveNXtv6MXcSAg87eBiyibg1qz3UXcohpYFVy8DQys9ogsLC11LKP1LNnNjyXQUqJ3RkS44Yzek2CbORFkBJjEu_h7_8fyJTcjaPTp3bn93DsiifItRaQcrx7fJzcECjM01pPGww)

2. Choose “kibana\_sample\_data\_ecommerce” as the source

\
![](https://lh5.googleusercontent.com/unNl8FzbKgf-0Azo9H0CLXSCiRHJd8BA3JDjQtjmPGVUbMrvsOMmMG-GmFG1ZrcYaAoommwRM6WDs8MWZKiBMARQvxLnP2Z3J0SetOfhXp6DnZFus-vLI_7FuZmvS9ycTSTFCUwqv17iQgK9rJzS4A)

3. Select “Pivot”, then in "Group by" enter **customer\_full\_name**

![](https://lh6.googleusercontent.com/Dd3zQlIO__lnq472yuudfdBf2P8Oke4cZhixYYxN93d64Odu3enrSMKW9MXqIghBrQOO4tkj5S75OUM7V3lg5Hq2831qNKPFIvokVfJbUffET-DI46tEXcaClPONODLtxyzZzQ18nzOM7xrj2fqhOQ)

4. Create the following column aggregations

   1. **order\_id.cardinality** 
   2. **taxful\_total\_price.sum**
   3. **products.quantity.sum**

Note: This just means that we are aggregating for each customer name:

1. The number of unique orders purchased to date
2. Total amount they've ever spent on the e-commerce store, and 
3. The total number of products they've ever bought (by summing those fields over all time)

![](https://lh6.googleusercontent.com/JH0ROVS9S7MHw5YdTnfK_TPQXaqeAdhAUkrDpBpv990sDtWFDB0eeoQjs03qmSe-l2BVwE2UjmbGKxzo3hgpKu5UsSmmEa5Pew-JoyZ7vVxcOVMqFZ8GMin2N529aBG3fP4FC4FjgLyHykH55zFb7w)

Click on the “**Next**” button to continue

\
![](https://lh5.googleusercontent.com/-wvCyaPz1OOYLXHs6_2YrMXIxj7RgV1oYtoeGSmPCSIT36kjzHztS9wT0HjWLpcFjyVsV9DmyZG-o31p-QFxO_LCA3ZIqPzmGEnTo377Vl09b8ILO3ajWCHSAHkQVW_UqqfjKSQ2BsFkY-DBlUN09g)

5. Name both the Transform ID and Destination Index as : “**lab3b\_ecomm\_customer\_sales**” and click on “**Next**”

\
![](https://lh6.googleusercontent.com/dmFSFSPeZOrWQkNE_b1dttrStk-wxjuzZtv8bmehDq8ySh_vNy4s28tTyU09iJkcFvO6VLtEhgKlDM3FYKNwpCtPU9J2yHIPpv4hDWTiZx8A7KQMqmcsJDYYtZHiIE7RGP7NVWiqxsz5Vjmm_5gOLQ)

6. Go ahead and click on the “**Create and Start**” button

![](https://lh3.googleusercontent.com/NHBz84TnkYUmTpc-sFNVWxUn8U4Ki_PhYuTMOejJ4iFG-wQW-KVs5fVok2JqC5cg0G2xgqhHNLHU-TVwQqiJMSch11p174d8AJ10vyBuRsAcDUvj5l-zRzHHjRB8XAs4JuNYlw24guDOBuJTQ_A_Hg)

7. After the job has completed, click **Discover** to see the new entity centric (transformed and summarized) index!

\
![](https://lh4.googleusercontent.com/K9bJFIe5lRj0KX60Z4pOihjpWYB_7lsCmlxKs84Y8ZGZzdmZIMIXziuir2r4ms4Z00BbUtoAv2vq5jsiTu4MxQ09vd-qgr0rLOElHSYa6h4aFWXsv-ehXWRUhRyGeUZ5yoWArut82lC3vsU6X7vgJw)

![](https://lh5.googleusercontent.com/sXtdroL7wd0yTZbUxZmtrHvxwnp5auQsGtnh7x9k-9uKOS2LnjGqeqAitneQla4nFakEYAmmRnNZP7hyYSwULIIAUvr58nlTXYV2oBUlvZz_3W2_CQEgexLVxFdWVYLYE4HdaWN5nXoyOdwNdHXQwg)

This was the first step, to get the data in this form - we can now analyze it further! Let's find the unusual shoppers!


## C - Outlier Detection

1. Click on **Kibana > Machine Learning > Data Frame Analytics link**.  Then click on “**Create job**”

\
![](https://lh5.googleusercontent.com/Zss5pT6nBjvovrsIOkBaE8eFnkBUnb2oixL5C0-MVsvQKeZEnUsHByLbHWTtsLiLqUkfxkyryc7q9IpEQ_SEdoHqoC4KuTn_Ks_4k-rs3hQwq8JA0tKnWorXYU1VTWc4Z__9llmcwQ9KSwOBNqqXeA)

2. Chose the lab3 transformed index: **“lab3b\_ecomm\_customer\_sales”**![](https://lh3.googleusercontent.com/8YlzpnwoOCJLzJqmsa4wMbODuF2spuxLCprxjXaMN7CxOeA0eE7OQuy09d45sNDSzFsS1vghqvJFuDBnwIBI6175fhu00fS0RNtYHyqJqPBo4qyJlNb3TwlyigfuKb8WVjbObHTKHxsOH3tmEAgF0A)

<!---->

3. Choose Job type as “**outlier detection**”.

   1. Click “**Continue**” in the “Configuration” section
   2. Click “**Continue**” in the “Additional Options”
   3. Give the name “**lab3c\_ecomm\_outliers**” as Job\_ID, click “**Continue**”
   4. Click “**Continue**” on the Validation section.
   5. Go ahead and click on the “**Create**” buttons.
   6. Click on “**Data Frame Analytics**”

\
![](https://lh4.googleusercontent.com/MwhxkBlGtolNi1E1p7SAdBSRkv4tpSgj2EhDtk53EVu7NnNLQJld58rIWezHYAFKVBxiZMb6Sm0eeFiZZ3DZSU97CmRwja9nETG-WvWcG5A9yDPuP554jBz4UC7kQs2AP_IrxA505J7TCws0n9cBSQ)

4. When the status of the job is “stopped” (it takes a few seconds), click on the “View” button to view the results

\
![](https://lh3.googleusercontent.com/WdhvsP7qi29nfylD-sWurozTRNIntC_-ljjuDB0RPsbLtGXlgXcTSOJ6j-a92yWhxOpaa2Bd259f85yGIYxH-OajfJKWuo7O3-d3pwYFI9alej6SalYOPnFXVGMj-ImsTCLIeh6v0HcMVIsTGJwudQ)

5. We are shown a data table with customers ranked by their outlier score.

The data frame analytics job creates an index that contains the original data and outlier scores for each document. The outlier score indicates how different each entity is from other entities.

Note that:

- The ml.outlier score is a value between 0 and 1. The larger the value, the more likely they are to be an outlier.
- In addition to an overall outlier score, each document is annotated with feature influence values for each field. These values add up to 1 and indicate which fields are the most important in deciding whether an entity is an outlier or inlier. For example, the dark shading on the products.taxful\_price.sum field for Wagdi Shaw indicates that the sum of the product prices was the most influential feature in determining that Wagdi is an outlier.

\
![](https://lh3.googleusercontent.com/Vdzr9E4HzGjZW74HBf-LnUufRkfFZ66M0fBFdPydyAVpMYINx48WOh9sgP-09UOlXA2hoqyQmE55RxlD7fViv8Z-8IfRHTg6HfKlwmf_VtcR0_bemsiWtC1qDNK1Au_i6Ah16OvOuObWPD1_qCM7fw)

---