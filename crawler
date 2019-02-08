import re
import urllib.request
import urllib.error

def crawl(url,page):
	req=urllib.request.Request(url)
	req.add_header("User-Agent","Mozilla/5.0(WindowsNT10.0;Win64;x64)AppleWebKit/537.36(KHTML,likeGecko)Chrome/52.0.2743.116Safari/537.36Edge/15.15063")
	data=str(urllib.request.urlopen(req).read())
	
	#正则表达式提取当前网页代码地址列表
	match1='<divid="plist".+?"pageclearfix">'
	result1=re.findall(match1,data)
	
	#进一步提取具体图片地址
	match2='<imgwidth="220"height="220"data-img="1"src="//.+?\.jpg">'
	imagelist=re.findall(match2,result1[0])
	
	for image in imagelist:
		#进一步提取可使用的图片地址
		match3='/img.+?\.jpg'
		result3=re.findall(match3,image)
		
		imageurl="http:/"+result3[0]
		imagename="Z:\\Downloads\\practise\\urllib\\downloadpic\\Page"+str(page)+"pic"+str(imagelist.index(image))+".jpg"
		
		try:
			#直接提取图片并保存到本地
			urllib.request.urlretrieve(imageurl,filename=imagename)
			#urlretrieve会产生缓存，提取后并清除缓存
			urllib.request.urlcleanup()
		except urllib.error.URLErrorase:
			ifhasattr(e,"code"):
				continue
			ifhasattr(e,"reason"):
				continue


for page in range(1,40):
	url="https://list.jd.com/list.html?cat=9987,653,655&ev=2943%5F67233&page="+str(page)
  crawl(url,page)
