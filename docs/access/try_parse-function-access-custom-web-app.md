---
title: 'Try_Parse Function (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed35263c-b0ad-4269-9caa-c0164015e980
description: 将文本值解析为数据类型区域性中的指定文本值，或返回 Null（如果转换无效）。
ms.openlocfilehash: 5d201557607d2d18c36238d9658b705a6a49fda8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427526"
---
# <a name="try_parse-function-access-custom-web-app"></a>Try_Parse Function (Access 自定义 Web 应用) 

将文本值解析为数据类型区域性中的指定文本值，或返回 Null（如果转换无效）。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

 **Try_Parse (** *TextExpression* *、DataType*)  
  
the **Try_Parse** function contains the following arguments. 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *TextExpression*  <br/> |一个文本表达式，代表要解析为指定值的格式数据类型。  <br/> |
| *DataType*  <br/> |用于数据类型  *TextExpression 的字符串*  。  <br/> |
   
## <a name="remarks"></a>备注

Use **Try_Parse** only for converting from string to date/time and number types. 对于常规类型转换，请继续使用 **Convert**。 
  

