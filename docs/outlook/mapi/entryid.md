---
title: ENTRYID
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.ENTRYID
api_type:
- COM
ms.assetid: 8ebb21ca-5ad1-4dcc-97b6-2390664b5d8d
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 8540176b7675917dde7c618c40142605e9622282
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22586219"
---
# <a name="entryid"></a>ENTRYID

  
  
**适用于**： Outlook 2013 |Outlook 2016 
  
包含一个 MAPI 对象的项标识符。 
  
|||
|:-----|:-----|
|头文件：  <br/> |Mapidefs.h  <br/> |
|相关的宏：  <br/> |[CbNewENTRYID](cbnewentryid.md) [SizedENTRYID](sizedentryid.md) <br/> |
   
```cpp
typedef struct
{
  BYTE abFlags[4];
  BYTE ab[MAPI_DIM];
} ENTRYID, FAR *LPENTRYID;

```

## <a name="members"></a>Members

 **abFlags**
  
> 提供描述对象的信息的标志的位掩码。 仅的第一个字节的标志， **abFlags [0]**，可以设置提供程序;保留其他三个。 永久的项标识符; 不能设置这些标志它们仅短期项标识符的设置。 向客户端，此结构是只读的。 可以在**abFlags [0]** 设置以下标志：
    
MAPI_NOTRECIP 
  
> 项标识符不能用作邮件收件人。
    
MAPI_NOTRESERVED 
  
> 其他用户无法访问的项标识符。
    
MAPI_NOW 
  
> 不能在其他情况下使用的项标识符。
    
MAPI_SHORTTERM 
  
> 短期的项标识符。 必须设置此字节中的所有其他值，除非已启用的项标识符的其他用途。
    
MAPI_THISSESSION 
  
> 不能在其他会话上使用的项标识符。
    
 **ab**
  
> 指示由服务提供商的二进制数据的数组。 客户端应用程序不能使用此数组。
    
## <a name="remarks"></a>注解

**ENTRYID**结构由消息存储和通讯簿提供程序来构造为它们的对象的唯一标识符。 条目标识符可用于确定以下类型的对象： 
  
- 消息存储库
    
- Folders
    
- 邮件
    
- 通讯簿容器
    
- 通讯组列表
    
- 邮件用户
    
- 状态对象
    
- 配置文件节
    
每个提供程序使用的提供程序有意义的**ENTRYID**结构格式。 
  
不能直接对条目标识符进行比较，因为一个对象可以由两个不同的二进制值表示。 若要确定两个条目标识符是否表示同一个对象，调用[IMAPISession::CompareEntryIDs](imapisession-compareentryids.md)方法。 
  
当客户端调用对象的[IMAPIProp::GetProps](imapiprop-getprops.md)方法来检索其条目标识符时，该对象返回的项标识符的最永久窗体。 客户端可以确认条目标识符长期通过检查**abFlags**成员的第一个字节设置任何标志。 
  
当客户端访问条目标识符通过最可能此条目标识符是短期而不是长期表中的列。 短期条目标识符可用于仅在当前的 MAPI 会话中打开其相应的对象。 客户端可以确认条目标识符短期通过检查所有标记中的第一个字节**abFlags**成员的设置。 
  
某些条目标识符短期，但具有长期使用。 此类条目标识符将有一个或多个设置其**abFlags**成员的第一个字节中的相应标志。 
  
**ENTRYID**结构类似于[FLATENTRY](flatentry.md)结构。 但是，有一些区别： 
  
- **ENTRYID**结构不存储的项标识符; 的大小**FLATENTRY**结构执行。 
    
- **ENTRYID**结构单独; 存储标志数据和项标识符的其余部分**FLATENTRY**结构用于存储与项标识符的其余部分标志数据。 
    
- 到[IMAPIProp](imapipropiunknown.md)接口的方法和以下**OpenEntry**方法，作为参数传递的**ENTRYID**结构： [IABLogon::OpenEntry](iablogon-openentry.md)， [IAddrBook::OpenEntry](iaddrbook-openentry.md)， [IMAPIContainer::OpenEntry](imapicontainer-openentry.md)， [IMAPISession::OpenEntry](imapisession-openentry.md) [IMAPISupport::OpenEntry](imapisupport-openentry.md)、 [IMsgStore::OpenEntry](imsgstore-openentry.md)、 [IMSLogon::OpenEntry](imslogon-openentry.md)
    
- **ENTRYID**结构用于存储在磁盘上的项标识符。 **FLATENTRY**结构用于存储在文件中的项标识符，或将其传递中的字节流。 
    
客户端应始终传入自然地对齐的条目标识符。 虽然提供程序应处理任意位置对齐的项标识符，但是客户端不应期望此行为。 未能将良好对齐的条目标识符传递给方法会导致对齐错误 RISC 处理器。 
  
自然对齐因素，通常为 8 个字节，是 CPU、 支持的最大数据类型和通常由系统内存分配程序相同的对齐方式系数。 自然地对齐的内存地址允许 CPU 访问它支持在该地址不生成对齐错误任何数据类型。 为 RISC Cpu 大小 N 的字节数的数据类型必须通常对齐上 N 个字节，甚至多正在从偶数多的地址
  
有关详细信息，请参阅[项标识符](mapi-entry-identifiers.md)。 
  
## <a name="see-also"></a>另请参阅



[FLATENTRY](flatentry.md)
  
[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)
  
[PidTagRecordKey 规范属性](pidtagrecordkey-canonical-property.md)


[MAPI 结构](mapi-structures.md)

