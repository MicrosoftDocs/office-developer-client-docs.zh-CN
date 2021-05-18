---
title: 'DateFromParts 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: 4fa49d5f-12ea-4d14-9a03-28418f01746c
description: 返回指定年份、月份和日期的日期值。
ms.openlocfilehash: 7d47fe93d1990365f1db5885a3ea8fc056aabb9f
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33423221"
---
# <a name="datefromparts-function-access-custom-web-app"></a>DateFromParts 函数 (Access 自定义 Web 应用) 

返回指定年份、月份和日期的日期值。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateFromParts** (*Year、Month、Day*)   
  
**DateFromParts** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Year*  <br/> |用于指定年份的整数表达式。  <br/> |
| *Month*  <br/> |用于指定月（从 1 到 12）的整数表达式。  <br/> |
| *Day*  <br/> |指定天的整数表达式。  <br/> |
   
## <a name="remarks"></a>备注

**DateFromParts** 返回日期值，其中日期部分设置为指定的年、月、日，时间部分设置为默认值。 如果参数为无效，则引发错误。 如果必需参数为 null，则返回 NULL。 
  
## <a name="example"></a>示例

下面的表达式使用 **DateFromParts** 函数计算当前月的第一天。 
  
`DateFromParts(Year(Today()),Month(Today()),1)`



