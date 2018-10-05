---
title: 关于在 Outlook 中设置地址列表的解析顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1589568-cb49-86dd-5d16-b08c8117bd17
description: 上次修改时间： 2012 年 7 月 5 日
ms.openlocfilehash: 07a4c3e90f686f291f95ff87f337b54d8bf35edc
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25391407"
---
# <a name="about-setting-the-resolution-order-for-address-lists-in-outlook"></a>关于在 Outlook 中设置地址列表的解析顺序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对于每个配置文件，Microsoft Office Outlook 支持多个地址列表和用户可以手动指定消息和会议请求中的与会者都已解析通过电子邮件中的收件人的地址列表的顺序。 例如，您可以设置解析顺序，以便姓名均已解析，首先对 Outlook 通讯簿，然后针对全局地址列表。 计算机上，用户可以打开通讯簿，单击**工具**和**选项**，以指定此解决方案顺序。 但是，在企业环境中，是面向 IT 管理员以编程方式设置按其姓名均已解析的地址列表的顺序更有效。 此类代码可以用作管理员部署在公司内启动自动化脚本的一部分。 
  
MAPI 支持在**[IAddrBook](iaddrbookimapiprop.md)** 界面中，以便您可以用于名称解析配置文件中设置新的搜索路径**[SetSearchPath](iaddrbook-getsearchpath.md)** 方法。 若要使用的**IAddrBook::SetSearchPath**方法，您必须指定所需要的分辨率顺序使用数组包含容器的相关地址簿解决它们的顺序。 该数组中的每个条目还应包含相应的通讯簿的条目 ID。 
  
下面是如何指定地址列表的自定义的搜索路径的代码示例。
  
- [以编程方式设置地址列表的解析顺序](how-to-programmatically-set-the-resolution-order-for-address-lists.md)
    
- [KB 292590： 如何更改与 SetSearchPath 通讯簿排序顺序](https://support.microsoft.com/kb/292590)
    

