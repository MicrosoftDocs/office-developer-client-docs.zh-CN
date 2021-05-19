---
title: IXPLogonAddressTypes
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IXPLogon.AddressTypes
api_type:
- COM
ms.assetid: 5add1f2b-d9e6-4d78-8739-c3848f6e32a3
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: ca68c604152a7a28fb6a5357aa9c012ec7466b5a
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33435374"
---
# <a name="ixplogonaddresstypes"></a>IXPLogon::AddressTypes

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回传输提供程序处理的收件人类型。
  
```cpp
HRESULT AddressTypes(
  ULONG FAR * lpulFlags,
  ULONG FAR * lpcAdrType,
  LPSTR FAR * FAR * lpppszAdrTypeArray,
  ULONG FAR * lpcMAPIUID,
  LPUID FAR * FAR * lpppUIDArray
);
```

## <a name="parameters"></a>参数

 _lpulFlags_
  
> [out]控制返回的字符串类型的标志位掩码。 可以设置以下标志：
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未MAPI_UNICODE，则字符串采用 ANSI 格式。
    
 _lpcAdrType_
  
> [out]指向  _lpppszAdrTypeArray_ 参数指向的数组中的条目计数的指针。 
    
 _lpppszAdrTypeArray_
  
> [out]指向指向标识收件人类型的字符串数组的指针的指针。
    
 _lpcMAPIUID_
  
> [out]指向  _lpppUIDArray_ 参数指向的数组中的条目计数的指针。 
    
 _lpppUIDArray_
  
> [out]指向指向指向标识收件人类型的 [MAPIUID](mapiuid.md) 结构的指针数组的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 传输提供程序已成功指示它可以处理的收件人类型。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

MAPI 后台处理程序在传输提供程序从对 [IXPProvider：：TransportLogon](ixpprovider-transportlogon.md)方法的调用返回后立即调用 **IXPLogon：：AddressTypes** 方法，以便传输提供程序可以指示它处理的收件人类型。 为表明这一点，传输提供程序应在  _lpppszAdrTypeArray_ 参数中传递回指向指向字符串的指针数组的指针，或传递回  _lpppUIDArray_ 参数指向 **指向 MAPIUID** 结构的指针数组的指针，或传递这两个参数中的值。 
  
这两个数组用于不同的标识过程。 MAPI 和 MAPI 后台处理程序使用 _lpppUIDArray_ 数组中的 [MAPIUID](mapiuid.md)结构标识由传输提供程序或传输提供程序连接到的邮件系统直接处理的收件人条目标识符。 MAPI 和 MAPI 后台处理程序都不通过使用这些 **MAPIUID** 结构中包含的条目标识符来扩展地址;这些结构仅用于收件人类型标识。 
  
MAPI 后台处理程序在决定哪个传输提供程序应处理出站邮件的哪些收件人时，将使用  _lpppszAdrTypeArray_ 参数中的每个字符串进行比较测试。 如果邮件收件人的 **PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性与标识传输提供程序提供的邮件地址类型之一的字符串完全匹配，则提供程序可以将邮件传递至该收件人。
  
如果多个传输提供程序可以处理同一类型的收件人，MAPI 将基于客户端应用程序的配置文件中指示的传输优先级顺序选择传输提供程序。 为了确定要使用哪个传输提供程序，MAPI 后台处理程序按优先级顺序扫描所有提供程序指定的 **MAPIUID** 结构，然后按优先级顺序扫描所有提供程序指定的地址类型值。 此扫描中与特定收件人匹配的第一个传输提供程序将第一次获得处理此收件人的机会。 如果该提供程序不处理收件人，MAPI 后台处理程序将继续扫描以查找任何尚未处理的收件人的传输提供程序。 扫描将继续，直到未找到任何进一步匹配项，此时会为未处理的任何收件人生成未送达报告。 
  
如果提供程序始终支持一组特定的收件人类型，则传输提供程序传递的地址类型和 **MAPIUID** 数组可以是静态的。 如果传输提供程序动态构造这些数组，它可以使用之前在调用 **TransportLogon** 时传递的支持对象来分配内存，尽管这不是必需的。
  
用于地址类型和 **MAPIUID** 数组的内存应保持分配状态，直到最终调用 [IXPLogon：：TransportLogoff](ixplogon-transportlogoff.md) 方法，传输提供程序在必要时可以释放内存。 传输提供程序在从 **TransportLogoff** 调用返回后不应更改这些数组的内容。 
  
可以处理任何类型的收件人的传输提供程序可以在  _lpppszAdrTypeArray_ 参数中返回 NULL。 基于 LAN 的邮件系统的传输提供程序，使用中央服务器将传出邮件发送到各种外消息系统通常可以这样做。 这种类型的传输提供程序应在配置文件中传输提供程序的 MAPI 和 MAPI 后台处理程序优先级顺序中最后安装。 
  
不支持根据地址类型调度到它的出站邮件的传输提供程序应在  _lpppszAdrTypeArray_ 中返回单个零长度字符串。 如果传输提供程序不支持收件人类型，则应该为 **MAPIUID** 结构传递 NULL，为地址类型传递空字符串。 此类型的传输提供程序最常用于安装邮件预处理器。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)
  
[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[MAPIUID](mapiuid.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

