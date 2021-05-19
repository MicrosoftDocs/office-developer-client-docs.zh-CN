---
title: OutlookSocial Connector 提供程序错误代码
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
ms.assetid: 0799243e-ba92-44c4-b687-182e50b57cb7
description: 提供程序应该使用下表中所示的错误代码之一将错误返回给调用方。
ms.openlocfilehash: 22a6e8d4ebf87157eaee630cc47f9f363150e839
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33425349"
---
# <a name="outlook-social-connector-provider-error-codes"></a>OutlookSocial Connector 提供程序错误代码

提供程序应该使用下表中所示的错误代码之一将错误返回给调用方。 
  
|**错误**|**错误代码 (十六进制)**|**说明**|
|:-----|:-----|:-----|
|OSC_E_AUTH_ERROR  <br/> |0x80041404  <br/> |社交网络网站的网络身份验证失败。  <br/> |
|OSC_E_COULDNOTCONNECT  <br/> |0x80041402  <br/> |无法连接到社交网络网站。  <br/> |
|OSC_E_FAIL  <br/> |0x80004005  <br/> |常规失败错误。  <br/> |
|OSC_E_INTERNAL_ERROR  <br/> |0x80041400  <br/> |由于操作无效而发生了内部错误。  <br/> |
|OSC_E_INVALIDARG (E_INVALIDARG)   <br/> |0x80070057  <br/> |向函数传递了无效参数。  <br/> |
|OSC_E_NO_CHANGES  <br/> |0x80041406  <br/> |自上次同步以来未发生任何更改。  <br/> |
|OSC_E_NOT_FOUND  <br/> |0x80041405  <br/> |找不到资源。  <br/> |
|OSC_E_NOT_IMPLEMENTED (E_NOTIMPL)   <br/> |0x80004001  <br/> |对社交网络网站的请求有效，但社交网络网站尚未实现。  <br/> |
|OSC_E_OUT_OF_MEMORY (E_OUTOFMEMORY)   <br/> |0x8007000E  <br/> |发生内存不足错误。  <br/> |
|OSC_E_PERMISSION_DENIED  <br/> |0x80041403  <br/> |OSC 提供程序拒绝对资源的权限。  <br/> |
|OSC_E_SERVER_VERSION_NOT_SUPPORTED  <br/> |0x80041406  <br/> |不支持用于配置社交网络帐户的服务器版本。  <br/> |
|OSC_E_VERSION  <br/> |0x80041401  <br/> |提供程序不支持此版本的 OSC 提供程序扩展性。  <br/> |
   
## <a name="remarks"></a>备注

通过使用称为结果句柄的 32 位数字或 **HRESULT** 返回成功、警告和错误值。 **HRESULT** 不是任何句柄;它只是一个 32 位值，该值中已编码多个字段。 正结果表示状态成功，零结果表示成功，状态 (S_OK) ，负结果表示失败。 
  

