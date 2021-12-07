### AIG_CityLifeAi_Instructions
* **Project Instructor:** Hao ZHENG
* **Developer**_(Back-end, Image Processing, Data Crawling)_: Zixun HUANG
* **Developer**_(Front-end, Interactive Design)_: Hang GAO
* **Network Training**: Hao ZHENG, Jingyi HE, Df2021(50-Professional Group)

# How to use the Test Website: 
1. You can access our web application service using our most recent **Test Address**: http://www.citylifeai.com:7007/
2. We briefly suspend the service on the mobile phone through detecting the page aspect ratio, due to some adaption issues discovered in the phone recently. So, keep the following in mind while launching the service: make sure it's running in **Full Screen** in Chrome on your PC.
3. If you can access the page, but not the internal services, such as registration, login, heat map prediction. Then please contact our backend developer (ME) or our instructor via email: "huangzxarchitecture@zju.edu.cn" or "zhhao@design.upenn.edu". 😀**JUST SEND ME A SIMPLE EMAIL AND I WILL GET BACK TO YOU AND KEEP THE SERVER-END ON MY LAPTOP ON FOR 72 HOURS!** 😀

Because the GPU resources deployed on cloud servers were not economical enough in the past, we temporarily deployed the trained neural network models locally, i.e., on the back-end developer's laptop. The back-end developer will provide predictive services to a public ip address via **frp** technology, which in turn will provide services to all other urban designers.

4. You can log-in with this Test Account: 13777458864; Password: zixun363837; Or enter any 11-digit number to create a new account.

# More about the frp version of our website
Frp is a fast reverse proxy to help you expose a local server behind a NAT or firewall to the Internet. See the demonstration about how our frp version work: https://youtu.be/djdg2VrfazU

# REST API
If you are a developer, you can access our services by following method with Postman, or you can also send requests through coding. (But, please make sure I don't go to bed and even close my laptop 🥱 ; Default URL _(baseurl7)_ for Your Developers' Requests: http://www.citylifeai.com:8883/ 
1. You can still login with the Test Account.
![a49bac145c85f914acec769a62d2433](https://user-images.githubusercontent.com/39406532/144711492-b0d0bfaf-a62c-457b-82aa-a8d76363151e.png)
2. A basic test to see if the server is up and running.
![cc297ff003dae1376c5f9f5febf8925](https://user-images.githubusercontent.com/39406532/144711660-ba6823b8-79a9-49a6-b0dd-04c17f9ccedc.png)
3. Upload your image via _input_label_ in the body and initialize the prediction to get the important **map_id** string.
(Some options not designed for the occasion: the _styled_map_ option can be the same as _input_label_, and the _latitude_ and _longitude_ can default to 120, 30)
![dea9bcb469ea774b48fa53f1dbb0e3b](https://user-images.githubusercontent.com/39406532/144711944-21bfa783-b59a-4298-befa-d1c2c32a077c.png)
_(Take the crime rate prediction as an example. "delivery", "easy_life", "findeasy", and "mobike2" are the remaining endpoints.)_
A test data-set for input labels: https://github.com/HUANGzixun1997/AIG_CityLifeAi/blob/main/test_dataSet.7z

4. Send a request to the URL: _{{baseurl7}}mlapi/**<map_id>**/map_run/_ for prediction result. You will get a matrix translated from the grey hot map, and the pixel positions of the 3 points with the highest thermal values in the image.
![773b3b4c0b815ee5fc7be6fdc07d0ba](https://user-images.githubusercontent.com/39406532/144712248-f72d6aed-caef-4309-9ffe-2f7825c12c30.png)
5. You can also access your visualization predictions at http://www.citylifeai.com:8883/media/**<map_id>**/results/synthesized_image_marked.jpg
![a356dec2fc8573c9d0c242a794916b9](https://user-images.githubusercontent.com/39406532/144712719-6cb22d29-3ba4-4d09-b72d-644d681fa054.png)

