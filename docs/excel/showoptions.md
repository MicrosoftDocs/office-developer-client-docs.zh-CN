---
title: ShowOptions
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 51acac58-ec39-488f-979c-1887dc2ab94b
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: dbf6f0f50e9f7fa988e83f3b58012e9deac13eac
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773814"
---
# <a name="showoptions"></a><span data-ttu-id="de4a7-103">ShowOptions</span><span class="sxs-lookup"><span data-stu-id="de4a7-103">ShowOptions</span></span>

<span data-ttu-id="de4a7-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="de4a7-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="de4a7-105">显示一个模式对话框，以从用户处收集信息。</span><span class="sxs-lookup"><span data-stu-id="de4a7-105">Shows a modal dialog box to collect information from the user.</span></span> <span data-ttu-id="de4a7-106">用户单击选定的群集连接器 （在**公式**部分下的**高级**类别中） 在**Excel 选项**对话框**群集类型**框旁边的**选项**按钮时调用此入口点。</span><span class="sxs-lookup"><span data-stu-id="de4a7-106">This entry point is called when a user clicks the **Options** button next to the **Cluster type** box for the selected cluster connector in the **Excel Options** dialog box (in the **Advanced** category under the **Formulas** section).</span></span> <span data-ttu-id="de4a7-107">群集连接器是负责实现自己选项对话框接口并存储在注册表中或其他位置的相关的数据。</span><span class="sxs-lookup"><span data-stu-id="de4a7-107">Cluster connectors are responsible for implementing their own options dialog interface and for storing the related data in the registry or elsewhere.</span></span> <span data-ttu-id="de4a7-108">选项都是内部人员到群集连接器。</span><span class="sxs-lookup"><span data-stu-id="de4a7-108">The options are internal to the cluster connector.</span></span> <span data-ttu-id="de4a7-109">Excel 不了解它们。</span><span class="sxs-lookup"><span data-stu-id="de4a7-109">Excel is not aware of them.</span></span> 
  
```cpp
int ShowOptions(HWND hWndParent)
```

## <a name="parameters"></a><span data-ttu-id="de4a7-110">参数</span><span class="sxs-lookup"><span data-stu-id="de4a7-110">Parameters</span></span>

<span data-ttu-id="de4a7-111">_hWndParent_</span><span class="sxs-lookup"><span data-stu-id="de4a7-111">_hWndParent_</span></span>
  
> <span data-ttu-id="de4a7-112">Excel 窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="de4a7-112">A handle to the Excel window.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="de4a7-113">返回值</span><span class="sxs-lookup"><span data-stu-id="de4a7-113">Return value</span></span>

<span data-ttu-id="de4a7-114">**xlHpcRetSuccess**如果对话框已显示;**xlHpcRetCallFailed**如果它不显示。</span><span class="sxs-lookup"><span data-stu-id="de4a7-114">**xlHpcRetSuccess** if the dialog box was shown; **xlHpcRetCallFailed** if it was not shown.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="de4a7-115">说明</span><span class="sxs-lookup"><span data-stu-id="de4a7-115">Remarks</span></span>

<span data-ttu-id="de4a7-116">群集连接器可以使用此对话框中获取信息，例如，若要使用，从用户哪些群集服务器。</span><span class="sxs-lookup"><span data-stu-id="de4a7-116">Cluster connectors can use this dialog box to get information, such as what cluster server to use, from the user.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de4a7-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="de4a7-117">See also</span></span>

- [<span data-ttu-id="de4a7-118">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="de4a7-118">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

