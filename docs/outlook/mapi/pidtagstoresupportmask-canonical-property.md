---
title: PidTagStoreSupportMask 规范属性
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.PidTagStoreSupportMask
api_type:
- COM
ms.assetid: ada5694a-b5b1-471f-be33-906fc052681a
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 143e7f0d2cd89cd4e7956cdda05d1bd512db4027
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32340969"
---
# <a name="pidtagstoresupportmask-canonical-property"></a>PidTagStoreSupportMask 规范属性

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
包含客户端应用程序查询以确定邮件存储特征的位掩码标志。 
  
|||
|:-----|:-----|
|相关属性：  <br/> |PR_STORE_SUPPORT_MASK  <br/> |
|标识符:  <br/> |0x340D  <br/> |
|数据类型：  <br/> |PT_LONG  <br/> |
|区域：  <br/> |其他  <br/> |
   
## <a name="remarks"></a>备注

此属性向计划向邮件发送的客户端应用程序公开邮件存储的功能。 该标志可以支持客户端或其他存储的决策，例如是发送 **PR_BODY** ([PidTagBody](pidtagbody-canonical-property.md)) 还是仅PR_RTF_COMPRESSED ([PidTagRtfCompressed](pidtagrtfcompressed-canonical-property.md)) 。  客户端永远不应设置 **PR_STORE_SUPPORT_MASK;** 尝试设置此标志将返回MAPI_E_COMPUTED。 
  
可以针对该位掩码设置以下一个或多个PR_STORE_SUPPORT_MASK标记：  
  
STORE_ANSI_OK
  
>  (131072 中，0x00020000) 邮件存储支持包含 ANSI (8 位字符) 属性。
    
STORE_ATTACH_OK 
  
>  (32 0x00000020) 邮件存储支持对邮件 (OLE 或非 OLE) 附件。 
    
STORE_CATEGORIZE_OK 
  
>  (1024 中，0x00000400) 邮件存储支持表的分类视图。 
    
STORE_CREATE_OK 
  
>  (16 0x00000010) 邮件存储支持新建邮件。 
    
STORE_ENTRYID_UNIQUE 
  
>  (1 0x00000001) ，邮件存储中对象的条目标识符是唯一的，即从不在存储生命周期中重复使用。 
    
STORE_HTML_OK 
  
>  (65536 中，0x00010000) 邮件存储支持 HTML 邮件，存储在 PR_BODY_HTML ( [PidTagBodyHtml](pidtagbodyhtml-canonical-property.md)) 属性中。 如果你的开发环境使用 MAPIDEFS。不包含值的 H STORE_HTML_OK，请改为使用 0x00010000 值。 
    
STORE_ITEMPROC
  
>  (2097152 0x00200000) 包装的 PST 存储中，指示当新邮件到达存储区时，该存储将单独对邮件执行规则和垃圾邮件筛选器处理。 存储调用 [IMAPISupport：：Notify](imapisupport-notify.md)，在作为参数传递的 [NOTIFICATION](notification.md)结构中设置 **fnevNewMail，** 然后将新消息的详细信息传递给侦听客户端。 随后，当侦听客户端收到通知，它不会处理邮件上的规则。 
    
STORE_LOCALSTORE
  
>  (524288，0x00080000) 保留此标志，不应使用。
    
STORE_MODIFY_OK 
  
>  (8，0x00000008) 邮件存储支持修改其现有邮件。 
    
STORE_MV_PROPS_OK 
  
>  (512， 0x00000200) 邮件存储支持多值属性，在整个保存操作中保证多值属性中值顺序的稳定性，并支持表中的多值属性实例化。 
    
STORE_NOTIFY_OK 
  
>  (256，0x00000100) 邮件存储支持通知。 
    
STORE_OLE_OK 
  
>  (64，0x00000040) 邮件存储支持 OLE 附件。 OLE 数据可通过 **IStorage** 接口访问，例如可通过 **PR_ATTACH_DATA_OBJ** ([PidTagAttachDataObject](pidtagattachdataobject-canonical-property.md)) 访问。 
    
STORE_PUBLIC_FOLDERS 
  
>  (16384 中，0x00004000) 此存储中的文件夹是公共 (多用户) ，而不是私有 (可能是多实例，但不是多用户) 。 
    
STORE_PUSHER_OK
  
>  (8388608 中，0x00800000) MAPI 协议处理程序将不会对存储进行爬网，存储负责通过通知将任何更改推送到索引器，以对邮件编制索引。
    
STORE_READONLY 
  
>  (2 0x00000002) ，邮件存储的所有接口具有只读访问级别。 
    
STORE_RESTRICTION_OK 
  
>  (4096，0x00001000) 邮件存储支持限制。 
    
STORE_RTF_OK 
  
>  (2048 0x00000800) 邮件存储支持 RTF 格式 (RTF) 邮件（通常已压缩）并且存储本身保持 PR_BODY 和 PR_RTF_COMPRESSED **同步。** 
    
STORE_RULES_OK
  
>  (268435456，0x10000000) 指示即使规则不是默认存储，也应存储在此 PST 存储中。 当 **STORE_RULES_OK** PST 包装存储区 **NON_EMS_XP_SAVE时，** 规则可以在非默认 PST 包装存储区中运行。
    
STORE_SEARCH_OK 
  
>  (4，0x00000004) 邮件存储支持搜索结果文件夹。 
    
STORE_SORT_OK 
  
>  (8192，0x00002000) 邮件存储支持表的排序视图。 
    
STORE_SUBMIT_OK 
  
>  (128 0x00000080) 邮件存储支持将邮件标记为提交。 
    
STORE_UNCOMPRESSED_RTF 
  
>  (32768 中，0x00008000) 邮件存储支持以未压缩的形式存储 RTF 邮件。 未压缩的 RTF 流由流标头中的 **值 dwMagicUncompressedRTF** 标识。 **dwMagicUncompressedRTF** 值在 RTFLIB 中定义。H 文件。 
    
STORE_UNICODE_OK
  
>  (262144 中，0x00040000) 指示邮件存储支持 Unicode 存储。 客户端可以查找标记以决定是否请求或将 Unicode 信息保存到存储区。 
    
始终可以存储邮件的 RTF 版本，即使邮件存储无法识别 RTF。 如果未为STORE_RTF_OK存储设置该位，则维护 RTF 版本的客户端必须自己调用 [RTFSync](rtfsync.md)函数，以保持文本内容的 PR_BODY 和 **PR_RTF_COMPRESSED** 版本的同步。  RTF 始终存储在PR_RTF_COMPRESSED，不管它是否实际压缩。 
  
## <a name="related-resources"></a>相关资源

### <a name="protocol-specifications"></a>协议规范

[[MS-OXPROPS]](https://msdn.microsoft.com/library/f6ab1613-aefe-447d-a49c-18217230b148%28Office.15%29.aspx)
  
> 提供对相关协议Exchange Server的引用。
    
[[MS-OXMSG]](https://msdn.microsoft.com/library/b046868c-9fbf-41ae-9ffb-8de2bd4eec82%28Office.15%29.aspx)
  
> 描述用于发送与客户端上的共享文件夹有关的信息的邮件的格式。
    
### <a name="header-files"></a>头文件

Mapidefs.h
  
> 提供数据类型定义。
    
Mapitags.h
  
> 包含作为备用名称列出的属性的定义。
    
## <a name="see-also"></a>另请参阅



[MAPI 属性](mapi-properties.md)
  
[MAPI 规范属性](mapi-canonical-properties.md)
  
[将规范属性名称映射到 MAPI 名称](mapping-canonical-property-names-to-mapi-names.md)
  
[将 MAPI 名称映射到规范属性名称](mapping-mapi-names-to-canonical-property-names.md)

