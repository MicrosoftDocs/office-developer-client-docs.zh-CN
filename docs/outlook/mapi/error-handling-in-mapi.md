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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287276"
---
# <a name="error-handling-in-mapi"></a>MAPI 中的错误处理

**适用于**：Outlook 2013 | Outlook 2016 
  
使用称为结果句柄或 HRESULT 的 32 位数字返回成功、警告和错误值。 HRESULT 实际上不是任何句柄;它只是一个 32 位值，值中编码了多个字段。 零结果表示成功，非零结果表示失败。
  
32 位平台上的 MAPI 仅适用于 HRESULT 值。
  
下图显示了 32 位平台的 HRESULT 格式。
  
**HRESULT 格式**
  
![HRESULT 格式](media/amapi_49.gif "HRESULT 格式")
  
HRESULT 中的高顺序位指示返回值是表示成功还是失败。 如果设置为零，则值表示成功。 如果设置为 1，则指示失败。
  
R、C、N 和 r 位保留在 HRESULT 中。
  
两个版本中的设备字段都指示错误的责任范围。 有许多设施，但绝大多数 MAPI 错误都FACILITY_ITF接口错误。 目前最常用的设施包括：FACILITY_NULL、FACILITY_ITF、FACILITY_DISPATCH、FACILITY_RPC 和 FACILITY_STORAGE。 如果需要新的设施，Microsoft 会分配它们，因为它们需要是唯一的。 下表介绍了各种设施字段。
  
|设施|说明|
|:-----|:-----|
|FACILITY_NULL  <br/> |For broadly applicable common status codes such as S_OK or E_OUTOF_MEMORY;值为 0。  <br/> |
|FACILITY_ITF  <br/> |对于大多数从接口方法返回的状态代码;值由 接口定义。 也就是说，两个 HRESULT 值与从两个不同接口返回的 32 位值完全相同，可能有不同的含义。  <br/> |
|FACILITY_DISPATCH  <br/> |对于晚期绑定 [IDispatch](https://msdn.microsoft.com/library/ms221608.aspx) 接口错误。  <br/> |
|FACILITY_RPC  <br/> |对于从远程过程调用返回的状态代码。  <br/> |
|FACILITY_STORAGE  <br/> |对于从与结构化存储相关的 [IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx) 或 [IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx) 方法调用返回的状态代码。 代码小于 16 位 () 值的范围为 Windows 错误代码 (即小于 256) 与对应的 Windows 错误具有相同的含义。  <br/> |
   
代码字段是分配用于表示错误或警告的唯一编号。
  

