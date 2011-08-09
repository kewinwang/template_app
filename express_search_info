#! /usr/bin/ruby 

# This file is a sample code for YouShang kuaidi
# For more information : www.kuaidi100.com
# 友商快递的API 

require "net/http"
require "Crack"
#require "json" # if return format is JSON
YOUSHANG_URL_BASE="http://api.kuaidi100.com/api?"   # API 接口
YOUSHANG_SITE_KEY="7023283d88021a76"                # 网站申请的API Key
com="yuantong"       # 快递公司的英文代号
number="1458222101"  # 快递的单号
query_url=YOUSHANG_URL_BASE+"id="+YOUSHANG_SITE_KEY+"&com="+com+"&nu="+number+"&show=0"+"&order=desc"
# show 查询返回的数据格式 0 默认的是JSON ，1返回的是XML 2 返回的是HTML 
# order 返回的查询信息的排列方式（按照时间的排序方式）
#result = JSON.parse(Net::HTTP.get(URI.parse(query_url)))
result=Crack::JSON.parse(Net::HTTP.get(URI.parse(query_url)))
# 如果返回的是XML 此处使用的是 Crack::XML.parse(.....)
# 输出查询的信息
if result && result["data"] && result["data"].size>=1
  result["data"].each do |data|
    puts   data["time"] + "---" + data["context"]
  end
end
