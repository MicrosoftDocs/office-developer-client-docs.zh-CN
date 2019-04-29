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
ms.openlocfilehash: 9e6901d6583e7a7924a4a7c19c0a262bcef74bd3
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435563"
---
# <a name="using-macros-for-error-handling"></a>使用宏进行错误处理

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
有几个宏可让您更轻松地使用 HRESULT 值。
  
有两组宏可测试是否出现故障或成功: HR_SUCCEEDED 和 HR_FAILED, 并且已成功和失败。 SUCCEEDED 与 HR_SUCCEEDED 相同, 失败与 HR_FAILED 相同。
  
在这种情况下, 使用**ResultFromScode**宏将 hresult 变量设置为 S_OK 的相应 HRESULT 值。 
  
常用的宏将在下表中简要说明。
  
|**宏**|**说明**|
|:-----|:-----|
|**MAKE_HRESULT** <br/> |从其组件构造 HRESULT。  <br/> |
|**HR_SUCCEEDED** <br/> |测试 HRESULT 的成功或警告条件。  <br/> |
|**HR_FAILED** <br/> |测试错误条件的 HRESULT。  <br/> |
|**HRESULT_CODE** <br/> |提取 HRESULT 的错误代码部分。  <br/> |
|**HRESULT_FACILITY** <br/> |从 HRESULT 中提取功能。  <br/> |
|**HRESULT_SEVERITY** <br/> |从严重性中提取严重度位。  <br/> |
|**完成** <br/> |测试 HRESULT 的成功或警告条件。  <br/> |
|**未能** <br/> |测试错误条件的 HRESULT。  <br/> |
   

