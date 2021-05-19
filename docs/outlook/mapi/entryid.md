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
|标头文件：  <br/> |Mapidefs.h  <br/> |
|相关宏：  <br/> |[CbNewENTRYID](cbnewentryid.md) [、SizedENTRYID](sizedentryid.md) <br/> |
   
```cpp
typedef struct
{
  BYTE abFlags[4];
  BYTE ab[MAPI_DIM];
} ENTRYID, FAR *LPENTRYID;

```

## <a name="members"></a>Members

 **abFlags**
  
> 提供描述对象的信息的标志的位掩码。 提供程序只能设置标志的第一个字节 **abFlags[0]**;其他三个已保留。 不得为永久条目标识符设置这些标志;它们仅为短期条目标识符设置。 对于客户端，此结构是只读的。 可以在 **abFlags[0] 中设置以下标志**：
    
MAPI_NOTRECIP 
  
> 条目标识符不能用作邮件上的收件人。
    
MAPI_NOTRESERVED 
  
> 其他用户无法访问条目标识符。
    
MAPI_NOW 
  
> 不能在其他时间使用条目标识符。
    
MAPI_SHORTTERM 
  
> 条目标识符为短期标识符。 必须设置此字节中的所有其他值，除非启用条目标识符的其他用法。
    
MAPI_THISSESSION 
  
> 条目标识符不能用于其他会话。
    
 **ab**
  
> 指示服务提供商使用的二进制数据数组。 客户端应用程序无法使用此数组。
    
## <a name="remarks"></a>备注

邮件存储和通讯簿提供程序使用 **ENTRYID** 结构来构造其对象的唯一标识符。 条目标识符用于标识以下类型的对象： 
  
- 邮件存储
    
- Folders
    
- 邮件
    
- 通讯簿容器
    
- 通讯组列表
    
- 邮件用户
    
- 状态对象
    
- 配置文件部分
    
每个提供程序都对 **ENTRYID** 结构使用一种格式，该格式对于该提供程序有意义。 
  
不能直接对条目标识符进行比较，因为一个对象可以由两个不同的二进制值表示。 若要确定两个条目标识符是否表示同一个对象，请调用 [IMAPISession：：CompareEntryIDs](imapisession-compareentryids.md) 方法。 
  
当客户端调用对象的 [IMAPIProp：：GetProps](imapiprop-getprops.md) 方法来检索其条目标识符时，该对象将返回条目标识符的最永久形式。 客户端可以通过检查 **abFlags** 成员的第一个字节中是否未设置任何标志来验证条目标识符是长期标识符。 
  
当客户端通过表中的列访问条目标识符时，很可能此条目标识符是短期标识符，而不是长期标识符。 短期条目标识符只能用于在当前 MAPI 会话中打开其相应的对象。 客户端可以通过检查在 **abFlags** 成员的第一个字节中设置所有标志来验证条目标识符是短期的。 
  
某些条目标识符是短期的，但具有长期用途。 此类条目标识符将在其 **abFlags** 成员的第一个字节中设置一个或多个相应标志。 
  
**ENTRYID** 结构类似于 [FLATENTRY](flatentry.md)结构。 但是，存在一些差异： 
  
- **ENTRYID** 结构不存储条目标识符的大小;**FLATENTRY** 结构有。 
    
- **ENTRYID** 结构单独存储标志数据和条目标识符的其余部分;**FLATENTRY** 结构使用条目标识符的其余部分存储标志数据。 
    
- **ENTRYID** 结构作为参数传递给 [IMAPIProp](imapipropiunknown.md)接口的方法和以下 **OpenEntry** 方法：IABLogon：：OpenEntry、IAddrBook：：OpenEntry、IMAPIContainer：：OpenEntry、IMAPISession：：OpenEntry、IMAPISupport：：OpenEntry、IMsgStore：：OpenEntry、IMSLogon：：OpenEntry [](iablogon-openentry.md) [](iaddrbook-openentry.md) [](imapicontainer-openentry.md) [](imapisession-openentry.md) [](imapisupport-openentry.md) [](imsgstore-openentry.md) [](imslogon-openentry.md)
    
- **ENTRYID** 结构用于在磁盘上存储条目标识符。 **FLATENTRY** 结构用于将条目标识符存储在文件中或传递到字节流中。 
    
客户端应始终传递自然对齐的条目标识符。 尽管提供程序应处理任意对齐的条目标识符，但客户端不应期望此行为。 如果未能将对齐良好的条目标识符传递给方法，可能会导致 RISC 处理器出现对齐错误。 
  
自然对齐因子（通常为 8 个字节）是 CPU 数据类型支持的最大对齐因子，并且通常是系统内存分配器使用的相同对齐因素。 自然对齐的内存地址允许 CPU 访问它数据类型该地址上支持的任何地址，而不会生成对齐错误。 对于 RISC CPU，数据类型 N 字节的大小通常必须在 N 字节的甚至倍数上对齐，地址为 N 的倍数。
  
有关详细信息，请参阅条目 [标识符](mapi-entry-identifiers.md)。 
  
## <a name="see-also"></a>另请参阅



[FLATENTRY](flatentry.md)
  
[IMAPISupport::CompareEntryIDs](imapisupport-compareentryids.md)
  
[PidTagRecordKey 规范属性](pidtagrecordkey-canonical-property.md)


[MAPI 结构](mapi-structures.md)

