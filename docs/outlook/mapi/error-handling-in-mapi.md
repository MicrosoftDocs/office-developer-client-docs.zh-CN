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
  
成功、警告和错误值使用32位数字 (称为结果句柄) 或 HRESULT 返回。 HRESULT 实际上不是任何一个句柄, 而是它只是一个32位值, 其中的多个字段编码在值中。 零结果表示成功, 而非零结果表示失败。
  
32位平台上的 MAPI 仅适用于 HRESULT 值。
  
下图显示了32位平台的 HRESULT 格式。
  
**HRESULT 格式**
  
![HRESULT 格式](media/amapi_49.gif "HRESULT 格式")
  
HRESULT 中的 high order bit 指示返回值是表示成功还是失败。 如果设置为 0, 则该值表示 "成功"。 如果设置为 1, 则表示失败。
  
在 HRESULT 中保留 r、C、N 和 r 位。
  
这两个版本中的 "设施" 字段指示错误的职责范围。 有几个功能, 但绝大多数 MAPI 错误都使用 FACILITY_ITF 表示接口错误。 当前使用的最常见的功能是: FACILITY_NULL、FACILITY_ITF、FACILITY_DISPATCH、FACILITY_RPC 和 FACILITY_STORAGE。 如果需要新设备, Microsoft 会对其进行分配, 因为它们需要是唯一的。 下表介绍了各种功能字段。
  
|设施|说明|
|:-----|:-----|
|FACILITY_NULL  <br/> |对于广泛适用的常见状态代码 (如 S_OK 或 E_OUTOF_MEMORY);值为零。  <br/> |
|FACILITY_ITF  <br/> |对于从接口方法返回的大多数状态代码;该值由接口定义。 也就是说, 两个 HRESULT 值与从两个不同的接口返回的32位值完全相同可能具有不同的含义。  <br/> |
|FACILITY_DISPATCH  <br/> |对于后期绑定[IDispatch](https://msdn.microsoft.com/library/ms221608.aspx)接口错误。  <br/> |
|FACILITY_RPC  <br/> |对于从远程过程调用返回的状态代码。  <br/> |
|FACILITY_STORAGE  <br/> |对于从[IStorage](https://msdn.microsoft.com/library/aa380015%28VS.85%29.aspx)或与结构化存储相关的[IStream](https://msdn.microsoft.com/library/aa380034%28VS.85%29.aspx)方法调用返回的状态代码。 在 windows 错误代码范围 (即, 小于 256) 中包含代码的状态代码 (低16位) 值与对应的 Windows 错误具有相同的含义。  <br/> |
   
"代码" 字段是分配给代表错误或警告的唯一编号。
  

