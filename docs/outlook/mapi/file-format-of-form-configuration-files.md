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
  
表单配置文件是由表单开发人员创建的用于定义表单的格式化文件。
  
由于表单管理员使用表单配置文件来加载表单，因此必须使用表单配置文件定义每个表单。 表单配置文件必须具有 .cfg 文件名扩展名。 该文件遵循文件初始化文件Windows的 (.ini语法) 。 

它分为多个命名部分，每个节包含一系列项和值。 值具有以下类型之一：字符串、显示字符串、平台字符串、路径、整数或全局唯一标识符 **GUID。** 可以使用能够保存文本文件的任何文本编辑器或字处理器创建表单配置文件。
  

