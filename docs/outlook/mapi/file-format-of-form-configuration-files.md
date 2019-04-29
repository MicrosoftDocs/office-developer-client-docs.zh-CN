---
title: 表单配置文件的文件格式
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 86e4ebd9-6df2-4346-9ce9-580f80a83884
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: d07d88d7b8b892a82832f91989e322ea3b32e040
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415549"
---
# <a name="file-format-of-form-configuration-files"></a>表单配置文件的文件格式

**适用于**：Outlook 2013 | Outlook 2016 
  
表单配置文件是由表单开发人员创建的格式文件, 用于定义表单。
  
由于表单管理器使用表单配置文件来加载表单, 因此必须使用表单配置文件定义每个表单。 表单配置文件的文件扩展名必须为. cfg。 该文件遵循 Windows 初始化文件 (.ini 文件) 的一般语法。 

它划分为已命名的部分, 每个部分包含一系列条目和值。 值具有以下类型之一: string、显示的字符串、平台字符串、path、integer 或全局唯一标识符 ( **GUID**)。 表单配置文件可使用能够保存文本文件的任何文本编辑器或字处理程序创建。
  

