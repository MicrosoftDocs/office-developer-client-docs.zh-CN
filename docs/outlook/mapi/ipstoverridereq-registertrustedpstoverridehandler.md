---
title: IPSTOVERRIDEREQRegisterTrustedPSTOverrideHandler
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
api_name:
- IPSTOVERRIDEREQ.RegisterTrustedPSTOverrideHandler
api_type:
- COM
ms.assetid: 4a73c77c-7e32-4302-bffe-a1ea13574731
description: 上次修改时间：2013 年 2 月 24 日
ms.openlocfilehash: acc0986dd80b549b0cb2b941a6937d47a4a959fe
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32279533"
---
# <a name="ipstoverridereqregistertrustedpstoverridehandler"></a><span data-ttu-id="d9d90-103">IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler</span><span class="sxs-lookup"><span data-stu-id="d9d90-103">IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler</span></span>

 
  
<span data-ttu-id="d9d90-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="d9d90-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="d9d90-105">启动个人文件夹的解锁过程 (.pst) 文件。</span><span class="sxs-lookup"><span data-stu-id="d9d90-105">Initiates the unlocking procedure for a Personal Folders (.pst) file.</span></span>
  
```cpp
HRESULT RegisterTrustedPSTOverrideHandler (
  LPCWSTR pwzDllPath, 
  LPVOID pvClientData
); 

```

## <a name="parameters"></a><span data-ttu-id="d9d90-106">参数</span><span class="sxs-lookup"><span data-stu-id="d9d90-106">Parameters</span></span>

 <span data-ttu-id="d9d90-107">_pwzDllPath_</span><span class="sxs-lookup"><span data-stu-id="d9d90-107">_pwzDllPath_</span></span>
  
> <span data-ttu-id="d9d90-108">[in]指向第三方动态链接库的路径的指针 (DLL) 。</span><span class="sxs-lookup"><span data-stu-id="d9d90-108">[in] A pointer to the path of a third-party dynamic-link library (DLL).</span></span>
    
 <span data-ttu-id="d9d90-109">_pvClientData_</span><span class="sxs-lookup"><span data-stu-id="d9d90-109">_pvClientData_</span></span>
  
> <span data-ttu-id="d9d90-110">[in]指向客户端数据的指针，PST 提供程序将该数据传递到对 DLL 的 HrTrustedPSTOverrideHandlerCallback 函数的后续调用中。</span><span class="sxs-lookup"><span data-stu-id="d9d90-110">[in] A pointer to client data, which will be passed by the PST provider into subsequent calls to the DLL's HrTrustedPSTOverrideHandlerCallback function.</span></span> <span data-ttu-id="d9d90-111">DLL 可能会使用此客户端数据来帮助验证是否应该解锁 PST。</span><span class="sxs-lookup"><span data-stu-id="d9d90-111">This client data may be used by the DLL to assist in verifying whether the PST should be unlocked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="d9d90-112">返回值</span><span class="sxs-lookup"><span data-stu-id="d9d90-112">Return value</span></span>

<span data-ttu-id="d9d90-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="d9d90-113">S_OK</span></span>
  
> <span data-ttu-id="d9d90-114">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="d9d90-114">The function call was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="d9d90-115">备注</span><span class="sxs-lookup"><span data-stu-id="d9d90-115">Remarks</span></span>

<span data-ttu-id="d9d90-116">wzDllPath 参数指定的 DLL 必须使用数字证书进行签名。</span><span class="sxs-lookup"><span data-stu-id="d9d90-116">The DLL specified by the wzDllPath parameter must be signed using a digital certificate.</span></span> <span data-ttu-id="d9d90-117">DLL 还必须导出具有以下签名的函数。</span><span class="sxs-lookup"><span data-stu-id="d9d90-117">The DLL must also export a function with the following signature.</span></span>
  
```
extern "C" HRESULT __cdecl HrTrustedPSTOverrideHandlerCallback(IMsgStore *pmstore, IUnknown *pOverride, LPVOID pvClientData)
```

<span data-ttu-id="d9d90-118">此函数的调用方式为：指向 PST 的 IMsgStore 对象的指针、指向实现 IPSTOVERRIDE1 接口的 IUnknown 对象的指针，以及指向最初通过 pvClientData 提供的数据的指针。</span><span class="sxs-lookup"><span data-stu-id="d9d90-118">This function will be called with a pointer to the IMsgStore object for the PST, a pointer to an IUnknown object that implements the IPSTOVERRIDE1 interface, and a pointer to the data originally supplied through pvClientData.</span></span>
  
<span data-ttu-id="d9d90-119">有关详细信息，请参阅[How to implement a PST override handler to bypass the PSTDisableGrow policy in Outlook 2007](https://support.microsoft.com/kb/956070)。</span><span class="sxs-lookup"><span data-stu-id="d9d90-119">For more information see [How to implement a PST override handler to bypass the PSTDisableGrow policy in Outlook 2007](https://support.microsoft.com/kb/956070).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d9d90-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d9d90-120">See also</span></span>



[<span data-ttu-id="d9d90-121">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d9d90-121">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md)
  
[<span data-ttu-id="d9d90-122">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="d9d90-122">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

