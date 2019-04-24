---
title: PidTagObjectType 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- PidTagObjectType
api_type:
- HeaderDef
ms.assetid: 37da4ff5-300d-479f-a8b4-6fc36df997d9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: b433db7cb157afbf8c3b506f2ed95b04b7b88564
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32329223"
---
# <a name="pidtagobjecttype-canonical-property"></a>PidTagObjectType 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含对象的类型。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_OBJECT_TYPE  <br/> |
|标识符:  <br/> |0x0FFE  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |常见  <br/> |
   
## <a name="remarks"></a>注解

此属性中包含的对象类型对应于可通过**OpenEntry**接口访问的对象的主接口。 它通常是通过咨询由相应的**OpenEntry**方法返回的_lpulObjType_参数来获取的。 以其他方式获取接口时, 调用[IMAPIProp:: GetProps](imapiprop-getprops.md)获取此属性的值。 
  
此属性可以具有下列值之一:
  
MAPI_ABCONT 
  
> 通讯簿容器对象 
    
MAPI_ADDRBOOK 
  
> 通讯簿对象 
    
MAPI_ATTACH 
  
> 邮件附件对象 
    
MAPI_DISTLIST 
  
> 通讯组列表对象 
    
MAPI_FOLDER 
  
> Folder 对象 
    
MAPI_FORMINFO 
  
> Form 对象 
    
MAPI_MAILUSER 
  
> 邮件用户对象 
    
MAPI_MESSAGE 
  
> Message 对象 
    
MAPI_PROFSECT 
  
> Profile 部分对象 
    
MAPI_SESSION 
  
> Session 对象 
    
MAPI_STATUS 
  
> Status 对象 
    
MAPI_STORE 
  
> 邮件存储对象
    
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[毫秒-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关 Exchange Server 协议规范的引用。
    
[[毫秒-OXOABK]](https://msdn.microsoft.com/library/f4cf9b4c-9232-4506-9e71-2270de217614%28Office.15%29.aspx)
  
> 指定用户、联系人、组和资源列表的属性和操作。
    
[[毫秒-NSPI]](https://msdn.microsoft.com/library/6dd0a3ea-b4d4-4a73-a857-add03a89a543%28Office.15%29.aspx)
  
> 处理客户端与名称服务提供程序接口 (NSPI) 服务器的通信。
    
[[毫秒-OXCFOLD]](https://msdn.microsoft.com/library/c0f31b95-c07f-486c-98d9-535ed9705fbf%28Office.15%29.aspx)
  
> 处理文件夹操作。
    
[[毫秒-OXCFXICS]](https://msdn.microsoft.com/library/b9752f3d-d50d-44b8-9e6b-608a117c8532%28Office.15%29.aspx)
  
> 处理客户端与服务器之间的数据传输的顺序和流。
    
[[毫秒-OXCMAIL]](https://msdn.microsoft.com/library/b60d48db-183f-4bf5-a908-f584e62cb2d4%28Office.15%29.aspx)
  
> 从 Internet 标准电子邮件约定转换为邮件对象。
    
[[毫秒-OXCMSG]](https://msdn.microsoft.com/library/7fd7ec40-deec-4c06-9493-1bc06b349682%28Office.15%29.aspx)
  
> 处理邮件和附件对象。
    
[[毫秒-OXOAB]](https://msdn.microsoft.com/library/b4750386-66ec-4e69-abb6-208dd131c7de%28Office.15%29.aspx)
  
> 指定本地通讯簿对象缓存的脱机通讯簿 (OAB) 文件格式。
    
[[毫秒-OXOMSG]](https://msdn.microsoft.com/library/daa9120f-f325-4afb-a738-28f91049ab3c%28Office.15%29.aspx)
  
> 指定允许用于电子邮件对象的属性和操作。
    
[[毫秒-OXOSRCH]](https://msdn.microsoft.com/library/c72e49b8-78c7-4483-ad65-e46e9133673b%28Office.15%29.aspx)
  
> 指定用于操作搜索文件夹列表配置的属性和操作。
    
### <a name="header-files"></a>头文件

mapidefs。h
  
> 提供数据类型定义。
    
Mapitags
  
> 包含列为关联属性的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

