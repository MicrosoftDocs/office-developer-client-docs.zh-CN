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
ms.openlocfilehash: c77acb5226361ce31a7f6b1694de7fe23f8dd71b
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33415269"
---
# <a name="entryid"></a>ENTRYID

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含 MAPI 对象的条目标识符。 
  
|||
|:-----|:-----|
|标头文件：  <br/> |mapidefs。h  <br/> |
|相关宏:  <br/> |[CbNewENTRYID](cbnewentryid.md)、 [SizedENTRYID](sizedentryid.md) <br/> |
   
```cpp
typedef struct
{
  BYTE abFlags[4];
  BYTE ab[MAPI_DIM];
} ENTRYID, FAR *LPENTRYID;

```

## <a name="members"></a>Members

 **abFlags**
  
> 提供描述对象的信息的标志的位掩码。 仅可由提供程序设置**abFlags [0]** 标志的第一个字节;另外三个是保留的。 不得为永久条目标识符设置这些标志;仅对短期条目标识符设置这些设置。 对于客户端, 此结构是只读的。 可以在**abFlags [0]** 中设置以下标志:
    
MAPI_NOTRECIP 
  
> 条目标识符不能用作邮件的收件人。
    
MAPI_NOTRESERVED 
  
> 其他用户无法访问条目标识符。
    
MAPI_NOW 
  
> 不能在其他时间使用条目标识符。
    
MAPI_SHORTTERM 
  
> 条目标识符是短期的。 除非启用了条目标识符的其他使用, 否则必须设置此字节中的所有其他值。
    
MAPI_THISSESSION 
  
> 条目标识符不能用于其他会话。
    
 **ab**
  
> 指示服务提供程序使用的二进制数据数组。 客户端应用程序无法使用此数组。
    
## <a name="remarks"></a>说明

" **ENTRYID** " 结构由邮件存储和通讯簿提供程序用于为其对象构造唯一标识符。 条目标识符用于标识以下类型的对象: 
  
- 邮件存储
    
- Folders
    
- 邮件
    
- 通讯簿容器
    
- 通讯组列表
    
- 邮件用户
    
- 状态对象
    
- 配置文件节
    
每个提供程序都使用对该提供商有意义的**ENTRYID**结构的格式。 
  
不能直接对条目标识符进行比较，因为一个对象可以由两个不同的二进制值表示。 若要确定两个条目标识符是否表示同一个对象, 请调用[IMAPISession:: CompareEntryIDs](imapisession-compareentryids.md)方法。 
  
当客户端调用对象的[IMAPIProp:: GetProps](imapiprop-getprops.md)方法以检索其条目标识符时, 该对象将返回条目标识符的最永久的形式。 客户端可以通过检查**abFlags**成员的第一个字节中是否未设置任何标志来验证条目标识符是否为长期。 
  
当客户端通过表中的列访问条目标识符时, 很可能此条目标识符是短期的, 而不是长期。 短期条目标识符可用于仅在当前 MAPI 会话中打开其对应的对象。 客户端可以通过检查**abFlags**成员的第一个字节中是否设置了所有标志来验证条目标识符是否为短期。 
  
某些条目标识符是短期的, 但长期使用。 这样的条目标识符将具有一个或多个在其**abFlags**成员的第一个字节中设置的合适的标志。 
  
**ENTRYID**结构类似于[FLATENTRY](flatentry.md)结构。 但是, 存在一些差异: 
  
- **ENTRYID**结构不存储条目标识符的大小;**FLATENTRY**结构。 
    
- **ENTRYID**结构单独存储项目标识符的标志数据和其余内容;**FLATENTRY**结构将标志数据与条目标识符的其余部分存储在一起。 
    
- **ENTRYID**结构作为参数传递给[IMAPIProp](imapipropiunknown.md)接口的方法和以下**OpenEntry**方法: [IABLogon:: OpenEntry](iablogon-openentry.md), [IAddrBook:: OpenEntry](iaddrbook-openentry.md), [IMAPIContainer:: OpenEntry](imapicontainer-openentry.md), [IMAPISession:: OpenEntry](imapisession-openentry.md), [IMAPISupport:: OpenEntry](imapisupport-openentry.md), [IMsgStore:: OpenEntry](imsgstore-openentry.md), [IMSLogon:: OpenEntry](imslogon-openentry.md)
    
- **ENTRYID**结构用于在磁盘上存储条目标识符。 **FLATENTRY**结构用于将条目标识符存储在文件中, 或将其传递到字节流中。 
    
客户端应始终传递以自然对齐的条目标识符。 虽然提供程序应处理任意对齐的条目标识符, 但客户端不应预期此行为。 如果未能将正确的条目标识符传递给方法, 则会导致 RISC 处理器上的校准错误。 
  
自然对齐因子 (通常为8个字节) 是 CPU 支持的最大数据类型, 通常与系统内存分配器使用相同的校准因子。 通过自然对齐的内存地址, CPU 可以访问它在该地址支持的任何数据类型, 而不会生成对齐错误。 对于 RISC cpu, 大小为 n 个字节的数据类型通常必须在 n 个字节的偶数倍进行对齐, 且地址是 n 的偶数倍。
  
有关详细信息, 请参阅[条目标识符](mapi-entry-identifiers.md)。 
  
## <a name="see-also"></a>另请参阅



[FLATENTRY](flatentry.md)
  
[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)
  
[PidTagRecordKey 规范属性](pidtagrecordkey-canonical-property.md)


[MAPI 结构](mapi-structures.md)

