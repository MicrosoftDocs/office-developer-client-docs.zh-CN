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
description: 上次修改时间： 2013 年 2 月 24 日
ms.openlocfilehash: acc0986dd80b549b0cb2b941a6937d47a4a959fe
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25393871"
---
# <a name="ipstoverridereqregistertrustedpstoverridehandler"></a><span data-ttu-id="6ea5e-103">IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler</span><span class="sxs-lookup"><span data-stu-id="6ea5e-103">IPSTOVERRIDEREQ::RegisterTrustedPSTOverrideHandler</span></span>

 
  
<span data-ttu-id="6ea5e-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="6ea5e-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="6ea5e-105">启动个人文件夹 (.pst) 文件的解除过程。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-105">Initiates the unlocking procedure for a Personal Folders (.pst) file.</span></span>
  
```cpp
HRESULT RegisterTrustedPSTOverrideHandler (
  LPCWSTR pwzDllPath, 
  LPVOID pvClientData
); 

```

## <a name="parameters"></a><span data-ttu-id="6ea5e-106">参数</span><span class="sxs-lookup"><span data-stu-id="6ea5e-106">Parameters</span></span>

 <span data-ttu-id="6ea5e-107">_pwzDllPath_</span><span class="sxs-lookup"><span data-stu-id="6ea5e-107">_pwzDllPath_</span></span>
  
> <span data-ttu-id="6ea5e-108">[in]一个指向第三方动态链接库 (DLL) 的路径。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-108">[in] A pointer to the path of a third-party dynamic-link library (DLL).</span></span>
    
 <span data-ttu-id="6ea5e-109">_pvClientData_</span><span class="sxs-lookup"><span data-stu-id="6ea5e-109">_pvClientData_</span></span>
  
> <span data-ttu-id="6ea5e-110">[in]一个指向客户端数据，将传入随后调用 DLL 的 HrTrustedPSTOverrideHandlerCallback 函数太平洋标准时间提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-110">[in] A pointer to client data, which will be passed by the PST provider into subsequent calls to the DLL's HrTrustedPSTOverrideHandlerCallback function.</span></span> <span data-ttu-id="6ea5e-111">此客户端数据可能由 DLL，用于帮助验证 PST 是否应解除锁定。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-111">This client data may be used by the DLL to assist in verifying whether the PST should be unlocked.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="6ea5e-112">返回值</span><span class="sxs-lookup"><span data-stu-id="6ea5e-112">Return value</span></span>

<span data-ttu-id="6ea5e-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6ea5e-113">S_OK</span></span>
  
> <span data-ttu-id="6ea5e-114">函数调用成功。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-114">The function call was successful.</span></span>
    
## <a name="remarks"></a><span data-ttu-id="6ea5e-115">说明</span><span class="sxs-lookup"><span data-stu-id="6ea5e-115">Remarks</span></span>

<span data-ttu-id="6ea5e-116">必须使用数字证书签名 wzDllPath 参数指定的 DLL。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-116">The DLL specified by the wzDllPath parameter must be signed using a digital certificate.</span></span> <span data-ttu-id="6ea5e-117">DLL 必须还导出带以下签名的函数。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-117">The DLL must also export a function with the following signature.</span></span>
  
```
extern "C" HRESULT __cdecl HrTrustedPSTOverrideHandlerCallback(IMsgStore *pmstore, IUnknown *pOverride, LPVOID pvClientData)
```

<span data-ttu-id="6ea5e-118">与指向 PST 的 IMsgStore 对象的、 指向实现 IPSTOVERRIDE1 接口，IUnknown 对象的指针和指向通过 pvClientData 最初提供数据的指针，将调用此函数。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-118">This function will be called with a pointer to the IMsgStore object for the PST, a pointer to an IUnknown object that implements the IPSTOVERRIDE1 interface, and a pointer to the data originally supplied through pvClientData.</span></span>
  
<span data-ttu-id="6ea5e-119">有关详细信息，请参阅[如何实现 PST 重写处理程序，以绕过 Outlook 2007 中的 PSTDisableGrow 策略](https://support.microsoft.com/kb/956070)。</span><span class="sxs-lookup"><span data-stu-id="6ea5e-119">For more information see [How to implement a PST override handler to bypass the PSTDisableGrow policy in Outlook 2007](https://support.microsoft.com/kb/956070).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6ea5e-120">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6ea5e-120">See also</span></span>



[<span data-ttu-id="6ea5e-121">IPSTOVERRIDE1 : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6ea5e-121">IPSTOVERRIDE1 : IUnknown</span></span>](ipstoverride1iunknown.md)
  
[<span data-ttu-id="6ea5e-122">IPSTOVERRIDEREQ : IUnknown</span><span class="sxs-lookup"><span data-stu-id="6ea5e-122">IPSTOVERRIDEREQ : IUnknown</span></span>](ipstoverridereqiunknown.md)

