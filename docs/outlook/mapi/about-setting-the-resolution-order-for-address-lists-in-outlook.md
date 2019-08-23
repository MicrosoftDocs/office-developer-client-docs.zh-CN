---
title: 关于设置在 Outlook 中地址列表的解析顺序
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: e1589568-cb49-86dd-5d16-b08c8117bd17
description: 上次修改时间：2012 年 7 月 5 日
ms.openlocfilehash: 07a4c3e90f686f291f95ff87f337b54d8bf35edc
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32321831"
---
# <a name="about-setting-the-resolution-order-for-address-lists-in-outlook"></a>关于设置在 Outlook 中地址列表的解析顺序

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
对于每个配置文件，Microsoft Office Outlook 支持多个地址列表，用户可以手动指定地址列表的顺序，按这个顺序解析电子邮件中的收件人和会议请求中的与会者。 例如，可以设置解析顺序，以便先按照 Outlook 通讯簿，再按照全局地址列表解析名称。 在计算机上，用户可以打开通讯簿，单击**工具**和**选项**指定这一解析顺序。 但是，在企业环境中，IT 管理员以编程方式设置解析名称的地址列表顺序会更有效。 此类代码可用作管理员在公司内部部署的启动自动化脚本的一部分。 
  
MAPI 支持 **[IAddrBook](iaddrbookimapiprop.md)** 界面中的 **[SetSearchPath](iaddrbook-getsearchpath.md)** 方法，允许您在用于名称解析的配置文件中设置新的搜索路径。 若要使用 **IAddrBook::SetSearchPath** 方法，您必须使用数组指定所需的解析顺序，该数组按照应该解析的顺序保存相关通讯簿的容器。 该数组中的每个条目还应包含相应通讯簿的条目 ID。 
  
以下是如何指定地址列表自定义搜索路径的代码示例。
  
- [以编程方式设置地址列表的解析顺序](how-to-programmatically-set-the-resolution-order-for-address-lists.md)
    
- [KB 292590：如何使用 SetSearchPath 更改通讯簿排序顺序](https://support.microsoft.com/kb/292590)
    

