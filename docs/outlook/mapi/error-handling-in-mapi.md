---
title: MAPI 中的错误处理
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
localization_priority: Normal
api_type:
- COM
ms.assetid: 99e2c485-af84-46f4-84b4-fca2117b5a21
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 98ee0856411cce3a3e9012185be6c30503de7779
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25401690"
---
# <a name="error-handling-in-mapi"></a>MAPI 中的错误处理

**适用于**：Outlook 2013 | Outlook 2016 
  
使用 32 位数字，因此已知句柄或 HRESULT 返回成功、 警告和错误值。 HRESULT 不真正是任何; 句柄它是只具有编码值中的多个字段的 32 位值。 零结果指示成功和非零结果指示故障。
  
在 32 位平台上的 MAPI 仅适用于 HRESULT 值。
  
下图显示了 32 位平台的 HRESULT 格式。
  
**HRESULT 格式**
  
![HRESULT 格式](media/amapi_49.gif "HRESULT 格式")
  
在 HRESULT 高位指示返回的值是否表示成功或失败。 如果设置为零，则值指示成功。 如果设置为 1，则表明失败。
  
R、 C、 N 和 r 位 HRESULT 中保留。
  
两个版本中的设施字段指示错误的责任的区域。 有几个设施，但绝大多数 MAPI 错误使用 FACILITY_ITF 表示界面错误。 当前使用的最常见功能是： FACILITY_NULL、 FACILITY_ITF、 FACILITY_DISPATCH、 FACILITY_RPC 和 FACILITY_STORAGE。 如果新设施是必需的 Microsoft 分配因为他们需要是唯一的。 下表介绍了各种的设施字段。
  
|设施|说明|
|:-----|:-----|
|FACILITY_NULL  <br/> |广泛适用常见的状态代码，如 S_OK 或 E_OUTOF_MEMORY;值为零。  <br/> |
|FACILITY_ITF  <br/> |大多数接口方法; 从返回的状态代码由接口定义值。 即两个的 HRESULT 值完全相同 32 位的值从两个不同接口返回的可能有不同的含义。  <br/> |
|FACILITY_DISPATCH  <br/> |为后期绑定[IDispatch](https://msdn.microsoft.com/library/ms221608.aspx)接口错误。  <br/> |
|FACILITY_RPC  <br/> |有关从远程过程调用的返回状态代码。  <br/> |
|FACILITY_STORAGE  <br/> |从与结构化存储有关[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)或[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)方法调用返回的状态代码。 状态代码中的范围的 Windows 错误代码的代码 （低 16 位） 值 (即，少于 256 个) 为相应的 Windows 错误意义相同。  <br/> |
   
代码字段是分配表示错误或警告的唯一编号。
  

