---
title: 'DateWithTimeFromParts 函数 (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
localization_priority: Normal
ms.assetid: aa97cbaa-8b14-42e3-a098-938ebe0769eb
description: 基于指定的年、月、日、时间返回日期和时间。
ms.openlocfilehash: ee995d346ca27e683f342cf3f611c1147997d24e
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33422087"
---
# <a name="datewithtimefromparts-function-access-custom-web-app"></a>DateWithTimeFromParts 函数 (Access 自定义 Web 应用) 

基于指定的年、月、日、时间返回日期和时间。
  
> [!NOTE]
> 本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。* > 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。 
  
## <a name="syntax"></a>语法

**DateWithTimeFromParts** (Year、Month、Day、Hour、Minute、Second)      
  
**DateWithTimeFromParts** 函数包含下列参数。 
  
|**参数名称**|**说明**|
|:-----|:-----|
| *Year*  <br/> |用于指定年份的整数表达式。  <br/> |
| *Month*  <br/> |指定月份整数表达式。  <br/> |
| *Day*  <br/> |指定天的整数表达式。  <br/> |
| *Hour*  <br/> |指定小时数的整数表达式。  <br/> |
| *Minute*  <br/> |指定分钟数的整数表达式。  <br/> |
| *Second*  <br/> |指定秒的整数表达式。  <br/> |
   
## <a name="remarks"></a>备注

**DateWithTimeFromParts** 返回完全初始化的 Date/Time 值。 如果参数是无效，将引发错误。 如果必需参数为 Null，则返回 Null。 
  

