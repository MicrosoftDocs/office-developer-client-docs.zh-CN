---
title: OpenStreamOnFile
manager: soliver
ms.date: 03/09/2015
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- MAPI.OpenStreamOnFile
api_type:
- COM
ms.assetid: 01fa459f-597d-4b16-b340-a79fb270cd71
description: 上次修改时间： 2015 年 3 月 9 日
ms.openlocfilehash: 8c246968dcac719a8ee8177e20e802f9c7033435
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19776570"
---
# <a name="openstreamonfile"></a><span data-ttu-id="24b94-103">OpenStreamOnFile</span><span class="sxs-lookup"><span data-stu-id="24b94-103">OpenStreamOnFile</span></span>

  
  
<span data-ttu-id="24b94-104">**适用于**： Outlook</span><span class="sxs-lookup"><span data-stu-id="24b94-104">**Applies to**: Outlook</span></span> 
  
<span data-ttu-id="24b94-105">分配并初始化 OLE **IStream**对象，以访问文件的内容。</span><span class="sxs-lookup"><span data-stu-id="24b94-105">Allocates and initializes an OLE **IStream** object to access the contents of a file.</span></span> <span data-ttu-id="24b94-106">此函数采用 ANSI 字符串所推荐的文件名称，包括的路径和文件扩展名，因此，使用此函数， [OpenStreamOnFileW](openstreamonfilew.md)，Unicode 版本。</span><span class="sxs-lookup"><span data-stu-id="24b94-106">This function takes an ANSI string as the file name including the path and the file extension, therefore, use of the Unicode version of this function, [OpenStreamOnFileW](openstreamonfilew.md), is recommended.</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24b94-107">头文件：</span><span class="sxs-lookup"><span data-stu-id="24b94-107">Header file:</span></span>  <br/> |<span data-ttu-id="24b94-108">Mapiutil.h</span><span class="sxs-lookup"><span data-stu-id="24b94-108">Mapiutil.h</span></span>  <br/> |
|<span data-ttu-id="24b94-109">通过实现：</span><span class="sxs-lookup"><span data-stu-id="24b94-109">Implemented by:</span></span>  <br/> |<span data-ttu-id="24b94-110">MAPI</span><span class="sxs-lookup"><span data-stu-id="24b94-110">MAPI</span></span>  <br/> |
|<span data-ttu-id="24b94-111">调用：</span><span class="sxs-lookup"><span data-stu-id="24b94-111">Called by:</span></span>  <br/> |<span data-ttu-id="24b94-112">客户端应用程序和服务提供商</span><span class="sxs-lookup"><span data-stu-id="24b94-112">Client applications and service providers</span></span>  <br/> |
   
```cpp
HRESULT STDMETHODCALLTYPE OpenStreamOnFile(
  LPALLOCATEBUFFER lpAllocateBuffer,
  LPFREEBUFFER lpFreeBuffer,
  ULONG ulFlags,
  LPSTR lpszFileName,
  LPSTR lpszPrefix,
  LPSTREAM FAR * lppStream
);
```

## <a name="parameters"></a><span data-ttu-id="24b94-113">参数</span><span class="sxs-lookup"><span data-stu-id="24b94-113">Parameters</span></span>

 <span data-ttu-id="24b94-114">_lpAllocateBuffer_</span><span class="sxs-lookup"><span data-stu-id="24b94-114">_lpAllocateBuffer_</span></span>
  
> <span data-ttu-id="24b94-115">[in]指向[MAPIAllocateBuffer](mapiallocatebuffer.md)函数，以用于分配内存。</span><span class="sxs-lookup"><span data-stu-id="24b94-115">[in] Pointer to the [MAPIAllocateBuffer](mapiallocatebuffer.md) function, to be used to allocate memory.</span></span> 
    
 <span data-ttu-id="24b94-116">_lpFreeBuffer_</span><span class="sxs-lookup"><span data-stu-id="24b94-116">_lpFreeBuffer_</span></span>
  
> <span data-ttu-id="24b94-117">[in]指向[MAPIFreeBuffer](mapifreebuffer.md)函数，以用于释放内存。</span><span class="sxs-lookup"><span data-stu-id="24b94-117">[in] Pointer to the [MAPIFreeBuffer](mapifreebuffer.md) function, to be used to free memory.</span></span> 
    
 <span data-ttu-id="24b94-118">_ulFlags_</span><span class="sxs-lookup"><span data-stu-id="24b94-118">_ulFlags_</span></span>
  
> <span data-ttu-id="24b94-119">[in]位掩码的标志用于控制创建或打开该文件的访问通过 OLE **IStream**对象。</span><span class="sxs-lookup"><span data-stu-id="24b94-119">[in] Bitmask of flags used to control the creation or opening of the file to be accessed through the OLE **IStream** object.</span></span> <span data-ttu-id="24b94-120">可以设置以下标志：</span><span class="sxs-lookup"><span data-stu-id="24b94-120">The following flags can be set:</span></span> 
    
<span data-ttu-id="24b94-121">SOF_UNIQUEFILENAME</span><span class="sxs-lookup"><span data-stu-id="24b94-121">SOF_UNIQUEFILENAME</span></span> 
  
> <span data-ttu-id="24b94-122">旨在为**IStream**对象创建一个临时文件。</span><span class="sxs-lookup"><span data-stu-id="24b94-122">A temporary file is to be created for the **IStream** object.</span></span> <span data-ttu-id="24b94-123">如果设置此标志，还应设置 STGM_CREATE 和 STGM_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="24b94-123">If this flag is set, the STGM_CREATE and STGM_READWRITE flags should also be set.</span></span> 
    
<span data-ttu-id="24b94-124">STGM_CREATE</span><span class="sxs-lookup"><span data-stu-id="24b94-124">STGM_CREATE</span></span> 
  
> <span data-ttu-id="24b94-125">文件是以创建即使已存在。</span><span class="sxs-lookup"><span data-stu-id="24b94-125">The file is to be created even if one already exists.</span></span> <span data-ttu-id="24b94-126">如果未设置_lpszFileName_参数，必须设置此标志和 STGM_DELETEONRELEASE。</span><span class="sxs-lookup"><span data-stu-id="24b94-126">If the  _lpszFileName_ parameter is not set, both this flag and STGM_DELETEONRELEASE must be set.</span></span> <span data-ttu-id="24b94-127">如果设置 STGM_CREATE，还必须设置 STGM_READWRITE 标志。</span><span class="sxs-lookup"><span data-stu-id="24b94-127">If STGM_CREATE is set, the STGM_READWRITE flag must also be set.</span></span> 
    
<span data-ttu-id="24b94-128">STGM_DELETEONRELEASE</span><span class="sxs-lookup"><span data-stu-id="24b94-128">STGM_DELETEONRELEASE</span></span> 
  
> <span data-ttu-id="24b94-129">文件是要删除在释放**IStream**对象时。</span><span class="sxs-lookup"><span data-stu-id="24b94-129">The file is to be deleted when the **IStream** object is released.</span></span> <span data-ttu-id="24b94-130">如果未设置_lpszFileName_参数，必须设置此标志和 STGM_CREATE。</span><span class="sxs-lookup"><span data-stu-id="24b94-130">If the  _lpszFileName_ parameter is not set, both this flag and STGM_CREATE must be set.</span></span> 
    
<span data-ttu-id="24b94-131">STGM_READ</span><span class="sxs-lookup"><span data-stu-id="24b94-131">STGM_READ</span></span> 
  
> <span data-ttu-id="24b94-132">文件是要创建或打开具有只读访问权限。</span><span class="sxs-lookup"><span data-stu-id="24b94-132">The file is to be created or opened with read-only access.</span></span> 
    
<span data-ttu-id="24b94-133">STGM_READWRITE</span><span class="sxs-lookup"><span data-stu-id="24b94-133">STGM_READWRITE</span></span> 
  
> <span data-ttu-id="24b94-134">文件是要创建或打开具有读/写权限。</span><span class="sxs-lookup"><span data-stu-id="24b94-134">The file is to be created or opened with read/write permission.</span></span> <span data-ttu-id="24b94-135">如果未设置此标志，STGM_CREATE 标志必须不设置之一。</span><span class="sxs-lookup"><span data-stu-id="24b94-135">If this flag is not set, the STGM_CREATE flag must not be set either.</span></span> 
    
 <span data-ttu-id="24b94-136">_lpszFileName_</span><span class="sxs-lookup"><span data-stu-id="24b94-136">_lpszFileName_</span></span>
  
> <span data-ttu-id="24b94-137">[in]文件名，包括路径和为其**OpenStreamOnFile**初始化**IStream**对象的文件扩展名。</span><span class="sxs-lookup"><span data-stu-id="24b94-137">[in] The filename, including path and extension, of the file for which **OpenStreamOnFile** initializes the **IStream** object.</span></span> <span data-ttu-id="24b94-138">如果设置了 SOF_UNIQUEFILENAME 标志， _lpszFileName_包含要在其中创建临时文件的目录的路径。</span><span class="sxs-lookup"><span data-stu-id="24b94-138">If the SOF_UNIQUEFILENAME flag is set,  _lpszFileName_ contains the path to the directory in which to create a temporary file.</span></span> <span data-ttu-id="24b94-139">如果_lpszFileName_为 NULL，则**OpenStreamOnFile**在系统中，获取适当的路径，且必须设置 STGM_CREATE 和 STGM_DELETEONRELEASE 标志。</span><span class="sxs-lookup"><span data-stu-id="24b94-139">If  _lpszFileName_ is NULL, **OpenStreamOnFile** obtains an appropriate path from the system, and both the STGM_CREATE and STGM_DELETEONRELEASE flags must be set.</span></span> 
    
 <span data-ttu-id="24b94-140">_lpszPrefix_</span><span class="sxs-lookup"><span data-stu-id="24b94-140">_lpszPrefix_</span></span>
  
> <span data-ttu-id="24b94-141">[in]用于在其**OpenStreamOnFile**初始化**IStream**对象的文件名的前缀。</span><span class="sxs-lookup"><span data-stu-id="24b94-141">[in] The prefix for the filename on which **OpenStreamOnFile** initializes the **IStream** object.</span></span> <span data-ttu-id="24b94-142">如果设置，前缀必须包含不能超过三个字符。</span><span class="sxs-lookup"><span data-stu-id="24b94-142">If set, the prefix must contain not more than three characters.</span></span> <span data-ttu-id="24b94-143">如果_lpszPrefix_为 NULL，则使用"SOF"的前缀。</span><span class="sxs-lookup"><span data-stu-id="24b94-143">If  _lpszPrefix_ is NULL, a prefix of "SOF" is used.</span></span> 
    
 <span data-ttu-id="24b94-144">_lppStream_</span><span class="sxs-lookup"><span data-stu-id="24b94-144">_lppStream_</span></span>
  
> <span data-ttu-id="24b94-145">[输出]为指向对象公开的**IStream**接口的指针。</span><span class="sxs-lookup"><span data-stu-id="24b94-145">[out] Pointer to a pointer to an object exposing the **IStream** interface.</span></span> 
    
## <a name="return-value"></a><span data-ttu-id="24b94-146">返回值</span><span class="sxs-lookup"><span data-stu-id="24b94-146">Return value</span></span>

<span data-ttu-id="24b94-147">S_OK</span><span class="sxs-lookup"><span data-stu-id="24b94-147">S_OK</span></span> 
  
> <span data-ttu-id="24b94-148">呼叫成功或多个预期值返回。</span><span class="sxs-lookup"><span data-stu-id="24b94-148">The call succeeded and has returned the expected value or values.</span></span> 
    
<span data-ttu-id="24b94-149">MAPI_E_NO_ACCESS</span><span class="sxs-lookup"><span data-stu-id="24b94-149">MAPI_E_NO_ACCESS</span></span> 
  
> <span data-ttu-id="24b94-150">由于用户权限不足，无法访问文件或因为无法修改只读文件。</span><span class="sxs-lookup"><span data-stu-id="24b94-150">The file could not be accessed due to insufficient user permissions or because read-only files cannot be modified.</span></span> 
    
<span data-ttu-id="24b94-151">MAPI_E_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="24b94-151">MAPI_E_NOT_FOUND</span></span> 
  
> <span data-ttu-id="24b94-152">指定的文件不存在。</span><span class="sxs-lookup"><span data-stu-id="24b94-152">The designated file does not exist.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="24b94-153">备注</span><span class="sxs-lookup"><span data-stu-id="24b94-153">Remarks</span></span>

<span data-ttu-id="24b94-154">**OpenStreamOnFile**函数有两个重要的用途，可分辨由 SOF_UNIQUEFILENAME 标志的设置。</span><span class="sxs-lookup"><span data-stu-id="24b94-154">The **OpenStreamOnFile** function has two important uses, distinguished by the setting of the SOF_UNIQUEFILENAME flag.</span></span> <span data-ttu-id="24b94-155">**OpenStreamOnFile**时未设置此标志，打开现有文件，例如，以将其内容复制到使用**IStream 附件的**PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) 属性**IStream**对象:: CopyTo**方法。</span><span class="sxs-lookup"><span data-stu-id="24b94-155">When this flag is not set, **OpenStreamOnFile** opens an **IStream** object on an existing file, for example to copy its contents to the **PR_ATTACH_DATA_BIN** ([PidTagAttachDataBinary](pidtagattachdatabinary-canonical-property.md)) property of an attachment using the **IStream::CopyTo** method.</span></span> <span data-ttu-id="24b94-156">在这种情况下_lpszFileName_参数指定的路径和文件的文件名。</span><span class="sxs-lookup"><span data-stu-id="24b94-156">In this case the  _lpszFileName_ parameter specifies the path and filename of the file.</span></span> 
  
<span data-ttu-id="24b94-157">当设置 SOF_UNIQUEFILENAME 时， **OpenStreamOnFile**创建临时文件来保存**IStream**对象的数据。</span><span class="sxs-lookup"><span data-stu-id="24b94-157">When SOF_UNIQUEFILENAME is set, **OpenStreamOnFile** creates a temporary file to hold data for an **IStream** object.</span></span> <span data-ttu-id="24b94-158">对于此用法， _lpszFileName_参数 （可选） 指定的目录的文件是要创建并_lpszPrefix_参数可以选择指定的文件名的前缀的路径。</span><span class="sxs-lookup"><span data-stu-id="24b94-158">For this usage, the  _lpszFileName_ parameter can optionally designate the path to the directory where the file is to be created, and the  _lpszPrefix_ parameter can optionally specify a prefix for the filename.</span></span> 
  
<span data-ttu-id="24b94-159">完成呼叫的客户端应用程序或服务提供商后与**IStream**对象，它应通过调用 OLE **IStream::Release**方法来进行释放。</span><span class="sxs-lookup"><span data-stu-id="24b94-159">When the calling client application or service provider is finished with the **IStream** object, it should free it by calling the OLE **IStream::Release** method.</span></span> 
  
<span data-ttu-id="24b94-160">MAPI 使用所指的_lpAllocateBuffer_和_lpFreeBuffer_对于大多数内存分配和释放，尤其是用于客户端应用程序分配内存，调用对象接口，如[IMAPIProp 时的功能：GetProps](imapiprop-getprops.md)和[IMAPITable::QueryRows](imapitable-queryrows.md)。</span><span class="sxs-lookup"><span data-stu-id="24b94-160">MAPI uses the functions pointed to by  _lpAllocateBuffer_ and  _lpFreeBuffer_ for most memory allocation and deallocation, in particular to allocate memory for use by client applications when calling object interfaces such as [IMAPIProp::GetProps](imapiprop-getprops.md) and [IMAPITable::QueryRows](imapitable-queryrows.md).</span></span> 
  
## <a name="notes-to-callers"></a><span data-ttu-id="24b94-161">给调用方的说明</span><span class="sxs-lookup"><span data-stu-id="24b94-161">Notes to callers</span></span>

<span data-ttu-id="24b94-162">SOF_UNIQUEFILENAME 标志用于创建特定于邮件系统名称的临时文件。</span><span class="sxs-lookup"><span data-stu-id="24b94-162">The SOF_UNIQUEFILENAME flag is used to create a temporary file with a name unique to the messaging system.</span></span> <span data-ttu-id="24b94-163">如果设置此标志， _lpszFileName_参数指定的路径的临时文件和_lpszPrefix_参数包含前缀字符的文件名。</span><span class="sxs-lookup"><span data-stu-id="24b94-163">If this flag is set, the  _lpszFileName_ parameter specifes the path for the temporary file, and the  _lpszPrefix_ parameter contains the prefix characters of the filename.</span></span> <span data-ttu-id="24b94-164">构造的文件名是<prefix>HHHH。TMP，其中 HHHH 是一个十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="24b94-164">The constructed filename is <prefix>HHHH.TMP, where HHHH is a hexadecimal number.</span></span> <span data-ttu-id="24b94-165">如果_lpszFileName_为 NULL，则将将从 Windows 函数**GetTempPath**，返回的临时文件目录或当前目录中创建文件，如果已指定没有临时文件目录。</span><span class="sxs-lookup"><span data-stu-id="24b94-165">If  _lpszFileName_ is NULL, the file will be created in the temporary file directory that is returned from the Windows function **GetTempPath**, or the current directory if no temporary file directory has been designated.</span></span> 
  
<span data-ttu-id="24b94-166">如果未设置 SOF_UNIQUEFILENAME 标志，则会忽略_lpszPrefix_ ，并且_lpszFileName_应包含的完全限定的路径和文件名的文件创建或打开。</span><span class="sxs-lookup"><span data-stu-id="24b94-166">If the SOF_UNIQUEFILENAME flag is not set,  _lpszPrefix_ is ignored, and  _lpszFileName_ should contain the fully qualified path and filename of the file to be opened or created.</span></span> <span data-ttu-id="24b94-167">将打开该文件，或创建基于其他_ulFlags_中设置的标志。</span><span class="sxs-lookup"><span data-stu-id="24b94-167">The file will be opened or created based on the other flags that are set in  _ulFlags_.</span></span> 
  
## <a name="mfcmapi-reference"></a><span data-ttu-id="24b94-168">MFCMAPI 参考 （英文）</span><span class="sxs-lookup"><span data-stu-id="24b94-168">MFCMAPI reference</span></span>

<span data-ttu-id="24b94-169">MFCMAPI 示例代码，请参阅下表。</span><span class="sxs-lookup"><span data-stu-id="24b94-169">For MFCMAPI sample code, see the following table.</span></span>
  
|<span data-ttu-id="24b94-170">**文件**</span><span class="sxs-lookup"><span data-stu-id="24b94-170">**File**</span></span>|<span data-ttu-id="24b94-171">**函数**</span><span class="sxs-lookup"><span data-stu-id="24b94-171">**Function**</span></span>|<span data-ttu-id="24b94-172">**Comment**</span><span class="sxs-lookup"><span data-stu-id="24b94-172">**Comment**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="24b94-173">File.cpp</span><span class="sxs-lookup"><span data-stu-id="24b94-173">File.cpp</span></span>  <br/> |<span data-ttu-id="24b94-174">WriteAttachStreamToFile</span><span class="sxs-lookup"><span data-stu-id="24b94-174">WriteAttachStreamToFile</span></span>  <br/> |<span data-ttu-id="24b94-175">MFCMAPI 使用**OpenStreamOnFile**方法打开文件流，因此附件可以写出到它。</span><span class="sxs-lookup"><span data-stu-id="24b94-175">MFCMAPI uses the **OpenStreamOnFile** method to open a stream on a file so an attachment can be written out to it.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="24b94-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24b94-176">See also</span></span>



[<span data-ttu-id="24b94-177">MFCMAPI 作为的代码示例</span><span class="sxs-lookup"><span data-stu-id="24b94-177">MFCMAPI as a Code Sample</span></span>](mfcmapi-as-a-code-sample.md)

