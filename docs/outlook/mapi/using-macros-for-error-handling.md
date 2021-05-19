---
title: 使用宏处理错误
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 351405ca-b72b-4e9e-bc8e-947344588970
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 9e6901d6583e7a7924a4a7c19c0a262bcef74bd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435563"
---
# <a name="using-macros-for-error-handling"></a>使用宏处理错误

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有几个宏可以更轻松地使用 HRESULT 值。
  
有两组宏用于测试失败或成功：HR_SUCCEEDED和HR_FAILED SUCCEEDED 和 FAILED。 SUCCEEDED 与 HR_SUCCEEDED 相同，FAILED 与 HR_FAILED。
  
在这种情况下，使用 **ResultFromScode** 宏将 HRESULT 变量设置为相应的 HRESULT S_OK。 
  
下表简要介绍了常用的宏。
  
|**宏**|**说明**|
|:-----|:-----|
|**MAKE_HRESULT** <br/> |从组件构造 HRESULT。  <br/> |
|**HR_SUCCEEDED** <br/> |测试 HRESULT 是否成功或警告条件。  <br/> |
|**HR_FAILED** <br/> |测试错误条件的 HRESULT。  <br/> |
|**HRESULT_CODE** <br/> |提取 HRESULT 的错误代码部分。  <br/> |
|**HRESULT_FACILITY** <br/> |从 HRESULT 中提取设施。  <br/> |
|**HRESULT_SEVERITY** <br/> |从 SEVERITY 中提取严重性位。  <br/> |
|**SUCCEEDED** <br/> |测试 HRESULT 是否成功或警告条件。  <br/> |
|**FAILED** <br/> |测试错误条件的 HRESULT。  <br/> |
   

