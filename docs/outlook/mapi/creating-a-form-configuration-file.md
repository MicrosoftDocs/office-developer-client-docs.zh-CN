---
title: 创建表单配置文件
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: aaf3b33d-ad2d-4ef8-847f-1ab1eaf08706
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 97ecafb2e4159c680fd23607f5ed6f8ea3156de7
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425216"
---
# <a name="creating-a-form-configuration-file"></a>创建表单配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单配置文件向使用的表单管理器和客户端应用程序提供有关表单的信息。 表单配置文件包含表单的扩展规范，包括由表单发布的供邮件客户端使用的属性、由表单实现动词以及表单支持的平台。
  
表单配置文件是扩展名为 .cfg 的文件，其格式类似于Windows文件。 它是一个包含许多节的纯文本文件。 每个节以节名称开头，括在方括号中。 每个节包含一行或多行，用于定义与节相关的值和设置。 值具有以下类型之一：
  
- String
    
- 显示的字符串
    
- 平台字符串
    
- 路径名称
    
- 整数
    
- GUID
    
有关 .cfg 文件的各个部分的信息，请参阅 File [Format of Form Configuration Files](file-format-of-form-configuration-files.md)。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

