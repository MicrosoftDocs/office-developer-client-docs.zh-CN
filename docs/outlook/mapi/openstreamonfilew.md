---
title: OpenStreamOnFileW
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- OpenStreamOnFileW
api_type:
- COM
ms.assetid: 263b9f24-eac8-4d34-8f66-dc87024b94b9
description: 上次修改时间：2015 年 3 月 9 日
ms.openlocfilehash: 7e67d84320b57fe6e510b70a68088f289ef6030d
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33406022"
---
# <a name="openstreamonfilew"></a>OpenStreamOnFileW

  
  
**适用于**：Outlook 2013 | Outlook 2016 
  
分配并初始化 OLE **IStream**对象以访问文件的内容。 此函数采用 UNICODE 字符串作为参数, 与此函数[OpenStreamOnFile](openstreamonfile.md)的 ANSI 版本不同, 因此允许文件名中包含路径和文件扩展名的任意字符。
  
|||
|:-----|:-----|
|导出者:  <br/> |olmapi32  <br/> |
|实现者：  <br/> |Outlook  <br/> |
|调用者：  <br/> |客户端应用程序和服务提供程序  <br/> |
   
```cpp
HRESULT STDMETHODCALLTYPE OpenStreamOnFileW(
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  LPWSTR lpszFileName,
  LPWSTR lpszPrefix,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a>参数

 _lpAllocateBuffer_
  
> 实时指向用于分配内存的[MAPIAllocateBuffer](mapiallocatebuffer.md)函数的指针。 
    
 _lpFreeBuffer_
  
> 实时指向用于释放内存的[MAPIFreeBuffer](mapifreebuffer.md)函数的指针。 
    
 _ulFlags_
  
> 实时用于控制要通过 OLE **IStream**对象访问的文件的创建或打开的标志的位掩码。 可以设置以下标志: 
    
SOF_UNIQUEFILENAME
  
> 将为**IStream**对象创建一个临时文件。 如果设置了此标志, 则还应设置 STGM_CREATE 和 STGM_READWRITE 标志。 
    
STGM_CREATE
  
> 即使已经存在文件, 也要创建文件。 如果未设置_lpszFileName_参数, 则必须设置此标志和 STGM_DELETEONRELEASE。 如果设置了 STGM_CREATE, 则还必须设置 STGM_READWRITE 标志。 
    
STGM_DELETEONRELEASE
  
> 释放**IStream**对象时, 将删除该文件。 如果未设置_lpszFileName_参数, 则必须设置此标志和 STGM_CREATE。 
    
STGM_READ
  
> 将使用只读访问权限创建或打开文件。
    
STGM_READWRITE
  
> 将使用读/写权限创建或打开文件。 如果未设置此标志, 则不得设置 STGM_CREATE 标志。
    
 _lpszFileName_
  
> 实时**OpenStreamOnFileW**为其初始化**IStream**对象的 Unicode 名为 file 的文件名, 包括路径和扩展名。 如果设置了 SOF_UNIQUEFILENAME 标志, 则_lpszFileName_包含要在其中创建临时文件的目录的路径。 如果_lpszFileName_为 NULL, 则**OpenStreamOnFileW**从系统中获取适当的路径, 并且必须设置 STGM_CREATE 和 STGM_DELETEONRELEASE 标志。 
    
 _lpszPrefix_
  
> 实时Unicode 文件名的前缀, **OpenStreamOnFileW**将在该文件名上初始化**IStream**对象。 如果设置, 则前缀必须包含三个以上的字符。 如果_lpszPrefix_为 NULL, 则使用前缀 "SOF"。 
    
 _lppStream_
  
> 排除指向公开**IStream**接口的对象的指针的指针。 
    
## <a name="return-value"></a>返回值

S_OK
  
> 调用成功, 并返回了所需的值或值。
    
MAPI_E_NO_ACCESS
  
> 由于用户权限不足或无法修改只读文件, 无法访问文件。
    
MAPI_E_NOT_FOUND
  
> 指定的文件不存在。
    
## <a name="remarks"></a>说明

除了处理具有 Unicode 名称的文件之外, **OpenStreamOnFileW**函数还有两个重要用途, 它们通过 SOF_UNIQUEFILENAME 标志的设置加以区分。 如果未设置此标志, 则**OpenStreamOnFileW**将在现有文件上打开**IStream**对象, 例如, 将其内容复制到使用**** 的[](pidtagattachdatabinary-canonical-property.md)**附件的 PR_ATTACH_DATA_BIN (PidTagAttachDataBinary) 属性。IStream:: CopyTo**方法。 在这种情况下, _lpszFileName_参数指定文件的路径和文件名。 
  
设置 SOF_UNIQUEFILENAME 后, **OpenStreamOnFileW**将创建一个临时文件, 用于保存**IStream**对象的数据。 在此用法中, _lpszFileName_参数可以选择指定要在其中创建文件的目录的路径, 并且_lpszPrefix_参数可以选择为文件名指定前缀。 
  
当调用客户端应用程序或服务提供程序完成了**IStream**对象时, 它应通过调用 OLE **IStream:: Release**方法来释放它。 
  
MAPI 使用_lpAllocateBuffer_和_lpFreeBuffer_指向的函数来实现大多数内存分配和释放, 尤其是在调用对象接口 (如[IMAPIProp::) 时分配供客户端应用程序使用的内存。GetProps](imapiprop-getprops.md)和[IMAPITable:: QueryRows](imapitable-queryrows.md)。 
  
## <a name="notes-to-callers"></a>给调用方的说明

SOF_UNIQUEFILENAME 标志用于创建具有邮件系统特有名称的临时文件。 如果设置了此标志, 则_lpszFileName_参数指定临时文件的路径, _lpszPrefix_参数包含文件名的前缀字符。 构造的文件名为<prefix>HHHH。TMP, 其中 HHHH 是一个十六进制数。 如果_lpszFileName_为 NULL, 则将在从 Windows 函数**GetTempPath**返回的临时文件目录中创建文件; 如果未指定临时文件目录, 则将在当前目录中创建文件。
  
如果未设置 SOF_UNIQUEFILENAME 标志, 则将忽略_lpszPrefix_ , 并且_lpszFileName_应包含要打开或创建的文件的完全限定路径和文件名。 将根据在_ulFlags_中设置的其他标志打开或创建文件。
  
## <a name="see-also"></a>另请参阅



[OpenStreamOnFile](openstreamonfile.md)

