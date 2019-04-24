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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32333017"
---
# <a name="creating-a-form-configuration-file"></a>创建表单配置文件

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
表单配置文件提供有关表单管理器使用的表单和客户端应用程序的信息。 表单配置文件包含表单的广泛规范, 包括由供邮件客户端使用的表单发布的属性、由表单实现的谓词以及表单支持的平台。
  
表单配置文件是扩展名为. cfg 的文件, 其格式与 Windows 初始化文件类似。 它是一个包含多个节的纯文本文件。 每个部分都以节名称开头, 并括在方括号中。 每个部分都包含一个或多个用于定义与该节相关的值和设置的行。 值具有以下类型之一:
  
- 字符串
    
- 显示的字符串
    
- 平台字符串
    
- 路径名称
    
- 整数
    
- GUID
    
有关 cfg 文件各部分的详细信息, 请参阅[文件格式的表单配置文件](file-format-of-form-configuration-files.md)。
  
## <a name="see-also"></a>另请参阅



[开发 MAPI 表单服务器](developing-mapi-form-servers.md)

