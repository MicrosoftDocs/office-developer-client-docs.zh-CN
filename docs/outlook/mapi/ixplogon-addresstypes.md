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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32357209"
---
# <a name="ixplogonaddresstypes"></a>IXPLogon::AddressTypes

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
返回传输提供程序处理的收件人的类型。
  
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
  
> 排除用于控制返回的字符串类型的标志的位掩码。 可以设置以下标志:
    
MAPI_UNICODE 
  
> 返回的字符串采用 Unicode 格式。 如果未设置 MAPI_UNICODE 标志, 则字符串将采用 ANSI 格式。
    
 _lpcAdrType_
  
> 排除一个指针, 指向由_lpppszAdrTypeArray_参数指向的数组中的项的计数。 
    
 _lpppszAdrTypeArray_
  
> 排除指向标识收件人类型的字符串数组的指针。
    
 _lpcMAPIUID_
  
> 排除一个指针, 指向由_lpppUIDArray_参数指向的数组中的项的计数。 
    
 _lpppUIDArray_
  
> 排除指向指向[MAPIUID](mapiuid.md)结构的指针的指针的指针, 该数组标识收件人类型。 
    
## <a name="return-value"></a>返回值

S_OK 
  
> 传输提供程序已成功指示其可以处理的收件人类型。
    
## <a name="notes-to-implementers"></a>针对实现者的说明

MAPI 后台处理程序在从对[IXPProvider:: TransportLogon](ixpprovider-transportlogon.md)方法的调用返回后立即调用**IXPLogon:: AddressTypes**方法, 以便传输提供程序可以指示其处理的收件人类型。 若要指明这一点, 传输提供程序应在_lpppszAdrTypeArray_参数中传递指向指向字符串的指针的指针, 或在_lpppUIDArray_参数中传回指向**MAPIUID**的指针的指针。结构或传递两个参数中的值。 
  
这两个数组用于不同的标识过程。 mapi 和 mapi 后台处理程序使用_lpppUIDArray_数组中的[MAPIUID](mapiuid.md)结构来标识那些由传输提供程序或由传输提供程序连接的邮件系统直接处理的收件人条目标识符。. mapi 和 mapi 后台处理程序都不通过使用其中任何一个**MAPIUID**结构中包含的条目标识符来展开地址;这些结构仅用于收件人类型标识。 
  
MAPI 后台处理程序使用_lpppszAdrTypeArray_参数中的每个字符串进行比较, 以便在决定哪种传输提供程序处理出站邮件的收件人时进行比较测试。 如果邮件收件人的**PR_ADDRTYPE** ([PidTagAddressType](pidtagaddresstype-canonical-property.md)) 属性与标识传输提供程序提供的邮件地址类型之一的字符串完全匹配, 则提供程序可以将邮件传递给该收件人。
  
如果多个传输提供程序可以处理相同类型的收件人, MAPI 将根据客户端应用程序配置文件中指示的传输优先级顺序选择传输提供程序。 若要确定要使用的传输提供程序, MAPI 后台处理程序将按优先级顺序扫描所有提供程序指定的**MAPIUID**结构, 然后按优先级顺序扫描所有提供程序指定的地址类型值。 第一个与此扫描中的特定收件人相匹配的传输提供程序将获得第一个处理此收件人的机会。 如果该提供程序未处理收件人, MAPI 后台处理程序将继续扫描, 以查找任何尚未处理的收件人的传输提供程序。 扫描将继续下去, 直到找不到更多的匹配项, 此时将为未处理的任何收件人生成 nondelivery 报告。 
  
如果提供程序始终支持一组特定的收件人类型, 则传输提供程序传递的地址类型和**MAPIUID**数组可以是静态的。 如果传输提供程序动态地构造这些数组, 则它可以使用之前在**TransportLogon**中传递的支持对象分配内存, 尽管这并不是必需的。
  
用于地址类型和**MAPIUID**数组的内存应一直分配到[IXPLogon:: TransportLogoff](ixplogon-transportlogoff.md)方法的最后一次调用, 此时传输提供程序可以释放内存 (如有必要)。 在从**TransportLogoff**调用返回之后, 传输提供程序不应更改这些数组的内容。 
  
可以处理任何类型的收件人的传输提供程序可以在_lpppszAdrTypeArray_参数中返回 NULL。 使用中央服务器将传出邮件传递给各种外部邮件系统的基于 LAN 的邮件系统的传输提供程序通常会执行此操作。 此类型的传输提供程序应在配置文件中的传输提供程序的 mapi 和 mapi 后台处理程序优先级顺序中进行最后安装。 
  
如果传输提供程序不支持根据地址类型为其分派的出站邮件, 则应在_lpppszAdrTypeArray_中返回单个零长度字符串。 如果传输提供程序不支持任何收件人类型, 则它应为**MAPIUID**结构传递 NULL, 并为该地址类型传递一个空字符串。 此类型的传输提供程序最常用于安装消息预处理器。 
  
## <a name="see-also"></a>另请参阅



[IXPLogon::TransportLogoff](ixplogon-transportlogoff.md)
  
[IXPProvider::TransportLogon](ixpprovider-transportlogon.md)
  
[MAPIUID](mapiuid.md)
  
[IXPLogon : IUnknown](ixplogoniunknown.md)

