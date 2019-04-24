---
title: Try_Parse 函数 (Access 自定义 web 应用程序)
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed35263c-b0ad-4269-9caa-c0164015e980
description: 将文本值分析为应用程序的区域性中的指定数据类型, 如果转换无效, 则返回 Null。
ms.openlocfilehash: 5d201557607d2d18c36238d9658b705a6a49fda8
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32307796"
---
# <a name="tryparse-function-access-custom-web-app"></a>Try_Parse 函数 (Access 自定义 web 应用程序)

将文本值分析为应用程序的区域性中的指定数据类型, 如果转换无效, 则返回 Null。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Try_Parse**(*TextExpression*, *DataType*) 
  
**Try_Parse**函数包含以下参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |表示要分析为指定数据类型的格式化值的文本表达式。  <br/> |
| *DataType*  <br/> |要在其中分析*TextExpression*的数据类型。  <br/> |
   
## <a name="remarks"></a>注解

仅使用**Try_Parse**将字符串转换为日期/时间和数字类型。 对于常规类型转换, 请继续使用**Convert**。 
  

