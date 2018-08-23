---
title: 使用宏进行错误处理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 351405ca-b72b-4e9e-bc8e-947344588970
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 715cd001c5eab89f40c31200a12deaf6981b9a61
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22567123"
---
# <a name="using-macros-for-error-handling"></a>使用宏进行错误处理

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
有几个宏的更方便地处理的 HRESULT 值。
  
有两组测试故障或成功的宏： HR_SUCCEEDED 和 HR_FAILED 和成功和失败。 成功是 HR_SUCCEEDED 和失败相同 HR_FAILED 相同。
  
在这种情况下，使用**ResultFromScode**宏 S_OK HRESULT 变量设置为相应的 HRESULT 值。 
  
下表简要介绍常用的宏。
  
|**宏**|**说明**|
|:-----|:-----|
|**MAKE_HRESULT** <br/> |构造 HRESULT 从及其组件。  <br/> |
|**HR_SUCCEEDED** <br/> |测试 HRESULT 成功或警告条件。  <br/> |
|**HR_FAILED** <br/> |测试 HRESULT 错误条件。  <br/> |
|**HRESULT_CODE** <br/> |提取 HRESULT 的错误代码部分。  <br/> |
|**HRESULT_FACILITY** <br/> |从 HRESULT 提取实用工具。  <br/> |
|**HRESULT_SEVERITY** <br/> |从严重提取严重性位。  <br/> |
|**成功** <br/> |测试 HRESULT 成功或警告条件。  <br/> |
|**失败** <br/> |测试 HRESULT 错误条件。  <br/> |
   

