---
title: Outlook Social Connector 提供程序错误代码
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0799243e-ba92-44c4-b687-182e50b57cb7
description: 提供程序将返回错误到呼叫者使用下表中显示的错误代码之一。
ms.openlocfilehash: 9e9abfda5930926a873ac37d3372eff7100be8a3
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19779326"
---
# <a name="outlook-social-connector-provider-error-codes"></a>Outlook Social Connector 提供程序错误代码

提供程序将返回错误到呼叫者使用下表中显示的错误代码之一。 
  
|**Error**|**错误代码 （十六进制）**|**说明**|
|:-----|:-----|:-----|
|OSC_E_AUTH_ERROR  <br/> |0x80041404  <br/> |身份验证失败的社交网络站点的网络上。  <br/> |
|OSC_E_COULDNOTCONNECT  <br/> |0x80041402  <br/> |可用于连接到社交网络站点没有连接。  <br/> |
|OSC_E_FAIL  <br/> |0x80004005  <br/> |一般故障时出错。  <br/> |
|OSC_E_INTERNAL_ERROR  <br/> |0x80041400  <br/> |由于无效操作发生内部错误。  <br/> |
|OSC_E_INVALIDARG (E_INVALIDARG)  <br/> |0x80070057  <br/> |无效的参数传递给函数。  <br/> |
|OSC_E_NO_CHANGES  <br/> |0x80041406  <br/> |上次同步后已不发生任何更改。  <br/> |
|OSC_E_NOT_FOUND  <br/> |0x80041405  <br/> |找不到资源。  <br/> |
|OSC_E_NOT_IMPLEMENTED (E_NOTIMPL)  <br/> |0x80004001  <br/> |对社交网络站点的请求有效，但未被执行由社交网络站点。  <br/> |
|OSC_E_OUT_OF_MEMORY (E_OUTOFMEMORY)  <br/> |0x8007000E  <br/> |内存不足时出错。  <br/> |
|OSC_E_PERMISSION_DENIED  <br/> |0x80041403  <br/> |OSC 提供程序拒绝的资源的权限。  <br/> |
|OSC_E_SERVER_VERSION_NOT_SUPPORTED  <br/> |0x80041406  <br/> |要配置的社交网络帐户的服务器版本不支持。  <br/> |
|OSC_E_VERSION  <br/> |0x80041401  <br/> |提供程序不支持此版本的 OSC 提供程序扩展性。  <br/> |
   
## <a name="remarks"></a>说明

使用 32 位数字后调用结果的句柄或**HRESULT**返回成功、 警告和错误值。 **HRESULT**不是任何; 的句柄它是只是 32 位的值，已编码值中的多个字段。 结果为正表示成功状态、 零结果表示状态 (S_OK)，不成功，结果为负表示失败。 
  

