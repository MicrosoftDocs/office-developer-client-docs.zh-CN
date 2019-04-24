---
title: ShowOptions
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 51acac58-ec39-488f-979c-1887dc2ab94b
description: 适用于： Excel 2013 | Office 2013 | Visual Studio
ms.openlocfilehash: 5b58b71dc4f2441448eb3e0dac2c3c5763675927
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32310425"
---
# <a name="showoptions"></a><span data-ttu-id="bfa9f-103">ShowOptions</span><span class="sxs-lookup"><span data-stu-id="bfa9f-103">ShowOptions</span></span>

<span data-ttu-id="bfa9f-104">**适用于** Excel 2013 | Office 2013 | Visual Studio</span><span class="sxs-lookup"><span data-stu-id="bfa9f-104">**Applies to**: Excel 2013 | Office 2013 | Visual Studio</span></span> 
  
<span data-ttu-id="bfa9f-105">显示一个模式对话框, 以收集用户的信息。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-105">Shows a modal dialog box to collect information from the user.</span></span> <span data-ttu-id="bfa9f-106">当用户单击 " **Excel 选项**" 对话框 (在 "**公式**" 部分下的 "**高级**" 类别中) 的 "**群集类型**" 框旁边的 "**选项**" 按钮时, 将调用此入口点。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-106">This entry point is called when a user clicks the **Options** button next to the **Cluster type** box for the selected cluster connector in the **Excel Options** dialog box (in the **Advanced** category under the **Formulas** section).</span></span> <span data-ttu-id="bfa9f-107">群集连接器负责实现其自己的 "选项" 对话框界面以及将相关数据存储在注册表或其他地方。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-107">Cluster connectors are responsible for implementing their own options dialog interface and for storing the related data in the registry or elsewhere.</span></span> <span data-ttu-id="bfa9f-108">选项是群集连接器的内部选项。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-108">The options are internal to the cluster connector.</span></span> <span data-ttu-id="bfa9f-109">Excel 并不知道它们。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-109">Excel is not aware of them.</span></span> 
  
```cpp
int ShowOptions(HWND hWndParent)
```

## <a name="parameters"></a><span data-ttu-id="bfa9f-110">参数</span><span class="sxs-lookup"><span data-stu-id="bfa9f-110">Parameters</span></span>

<span data-ttu-id="bfa9f-111">_hWndParent_</span><span class="sxs-lookup"><span data-stu-id="bfa9f-111">_hWndParent_</span></span>
  
> <span data-ttu-id="bfa9f-112">Excel 窗口的句柄。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-112">A handle to the Excel window.</span></span>
    
## <a name="return-value"></a><span data-ttu-id="bfa9f-113">返回值</span><span class="sxs-lookup"><span data-stu-id="bfa9f-113">Return value</span></span>

<span data-ttu-id="bfa9f-114">如果显示对话框, 则为**xlHpcRetSuccess** ;如果未显示**xlHpcRetCallFailed** , 则为。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-114">**xlHpcRetSuccess** if the dialog box was shown; **xlHpcRetCallFailed** if it was not shown.</span></span> 
  
## <a name="remarks"></a><span data-ttu-id="bfa9f-115">注解</span><span class="sxs-lookup"><span data-stu-id="bfa9f-115">Remarks</span></span>

<span data-ttu-id="bfa9f-116">群集连接器可以使用此对话框从用户处获取信息 (如要使用哪个群集服务器)。</span><span class="sxs-lookup"><span data-stu-id="bfa9f-116">Cluster connectors can use this dialog box to get information, such as what cluster server to use, from the user.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="bfa9f-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bfa9f-117">See also</span></span>

- [<span data-ttu-id="bfa9f-118">Excel 群集连接器函数</span><span class="sxs-lookup"><span data-stu-id="bfa9f-118">Excel Cluster Connector Functions</span></span>](excel-cluster-connector-functions.md)

