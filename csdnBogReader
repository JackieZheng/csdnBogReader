// ==UserScript==
// @name         CSDN博客阅读模式切换插件 
// @version      1.5
// @description  CSDN 阅读模式和浏览模式切换，完美支持傲游、360、Chrome等浏览器
// @author       By Jackie http://csdn.admans.cn/
// @match        *://blog.csdn.net/*/article/details/*
// @grant    GM_addStyle
// @namespace https://greasyfork.org/users/164689
// ==/UserScript==

GM_addStyle("#ReadBtn{position: relative;float: right;width: auto;background: #0f962191;z-index: 99;color: white;text-align: center;margin: 5px;padding: 5px;border-radius: 5px;cursor: pointer;}");
GM_addStyle(".html_body_readmodel{overflow: hidden;}");
GM_addStyle(".article_content_readmodel{position: fixed !important;top: 0px;left: 0px;width: 100%;z-index: 999;overflow: auto;height: 100%;background: white;padding: 20px;border:10px solid #bce4cba8;}");
GM_addStyle(".readBtn_float{position: fixed !important;right: 40px;}");
GM_addStyle(".markdown_views img{margin:24px auto !important;display: flow-root;}");
GM_addStyle(".htmledit_views img{margin:24px auto !important;display: flow-root;}");
(function(){
        'use strict';
          var divView = document.createElement("div");
          divView.setAttribute("id", "ReadBtn");
          divView.innerHTML ='阅读模式';          
          var article=document.getElementsByClassName('article_content')[0];
          article.insertBefore(divView,article.childNodes[0]); 
          //自动展开文章内容
          var readMoreBtn=document.getElementById('btn-readmore')
          if(readMoreBtn){readMoreBtn.click(); }
          
          divView.onclick=function()
          {
              if(divView.innerHTML=='阅读模式')
              {
                  divView.innerHTML ='浏览模式';
                  addClass(article,"article_content_readmodel");
                  addClass(document.body,"html_body_readmodel");
                  addClass(divView,"readBtn_float");                
              }
              else
             {             
                  divView.innerHTML ='阅读模式';              
                  removeClass(article,"article_content_readmodel");
                  removeClass(document.body,"html_body_readmodel");
                  removeClass(divView,"readBtn_float"); 
             }
          }
          
       
          
            
        //检测样式
        function hasClass(ele, cls) {
          return ele.className.match(new RegExp("(\\s|^)" + cls + "(\\s|$)"));
        }
        //添加样式
        function addClass(ele, cls) {
            if (!hasClass(ele, cls)) ele.className += " " + cls;
        }
        //删除样式
        function removeClass(ele, cls) {
            if (hasClass(ele, cls)) {
                var reg = new RegExp("(\\s|^)" + cls + "(\\s|$)");
                ele.className = ele.className.replace(reg, " ");
            }
        }  
    })();
