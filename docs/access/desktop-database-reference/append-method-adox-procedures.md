---
title: Append 方法（ADOX 过程）
TOCTitle: Append method (ADOX Procedures)
ms:assetid: a93b31bb-e41a-5152-abe7-dd7c2b2fcd0a
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249783(v=office.15)
ms:contentKeyID: 48546919
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: a2de9dc7d8dccfc4107dbd802c4013ac794acf61
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28704845"
---
# <a name="append-method-adox-procedures"></a><span data-ttu-id="a5147-102">Append 方法（ADOX 过程）</span><span class="sxs-lookup"><span data-stu-id="a5147-102">Append method (ADOX Procedures)</span></span>

<span data-ttu-id="a5147-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a5147-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a5147-104">将新的 [Procedure](procedure-object-adox.md) 对象添加到 [Procedures](procedures-collection-adox.md) 集合。</span><span class="sxs-lookup"><span data-stu-id="a5147-104">Adds a new [Procedure](procedure-object-adox.md) object to the [Procedures](procedures-collection-adox.md) collection.</span></span>

## <a name="syntax"></a><span data-ttu-id="a5147-105">语法</span><span class="sxs-lookup"><span data-stu-id="a5147-105">Syntax</span></span>

<span data-ttu-id="a5147-106">*过程*。追加*名称*，*命令*</span><span class="sxs-lookup"><span data-stu-id="a5147-106">*Procedures*.Append*Name*, *Command*</span></span>

## <a name="parameters"></a><span data-ttu-id="a5147-107">Parameters</span><span class="sxs-lookup"><span data-stu-id="a5147-107">Parameters</span></span>

|<span data-ttu-id="a5147-108">参数</span><span class="sxs-lookup"><span data-stu-id="a5147-108">Parameter</span></span>|<span data-ttu-id="a5147-109">说明</span><span class="sxs-lookup"><span data-stu-id="a5147-109">Description</span></span>|
|:--------|:----------|
|<span data-ttu-id="a5147-110">*Name*</span><span class="sxs-lookup"><span data-stu-id="a5147-110">*Name*</span></span> |<span data-ttu-id="a5147-111">**String** 值，指定要创建并追加的过程的名称。</span><span class="sxs-lookup"><span data-stu-id="a5147-111">A **String** value that specifies the name of the procedure to create and append.</span></span>|
|<span data-ttu-id="a5147-112">*Command*</span><span class="sxs-lookup"><span data-stu-id="a5147-112">*Command*</span></span> |<span data-ttu-id="a5147-113">一个 ADO [Command](command-object-ado.md) 对象，表示要创建并追加的过程。</span><span class="sxs-lookup"><span data-stu-id="a5147-113">An ADO [Command](command-object-ado.md) object that represents the procedure to create and append.</span></span>|

## <a name="remarks"></a><span data-ttu-id="a5147-114">备注</span><span class="sxs-lookup"><span data-stu-id="a5147-114">Remarks</span></span>

<span data-ttu-id="a5147-115">使用在 **Command** 对象中指定的名称和属性在数据源中创建一个新过程。</span><span class="sxs-lookup"><span data-stu-id="a5147-115">Creates a new procedure in the data source with the name and attributes specified in the **Command** object.</span></span>

<span data-ttu-id="a5147-p101">如果用户指定的命令文本表示视图而非过程，则其行为取决于所使用的提供程序。如果该提供程序不支持保留命令，则 **Append** 将失败。</span><span class="sxs-lookup"><span data-stu-id="a5147-p101">If the command text that the user specifies represents a view rather than a procedure, the behavior is dependent upon the provider being used. **Append** will fail if the provider does not support persisting commands.</span></span>

> [!NOTE]
> <span data-ttu-id="a5147-118">使用 Microsoft Jet OLE DB 提供程序，将允许**Procedures**集合的**Append**方法，您可以在*命令*参数中指定**视图**，而不是**过程**。</span><span class="sxs-lookup"><span data-stu-id="a5147-118">When using the OLE DB Provider for Microsoft Jet, the **Procedures** collection **Append** method will allow you to specify a **View** rather than a **Procedure** in the *Command* parameter.</span></span> <span data-ttu-id="a5147-119">该 **View** 将添加到数据源，并将添加到 **Procedures** 集合。</span><span class="sxs-lookup"><span data-stu-id="a5147-119">The **View** will be added to the data source and will be added to the **Procedures** collection.</span></span> <span data-ttu-id="a5147-120">执行 **Append** 之后，如果刷新 **Procedures** 和 **Views** 集合，可以看见该 **View** 不再位于 **Procedures** 集合中，而是出现在 **Views** 集合中。</span><span class="sxs-lookup"><span data-stu-id="a5147-120">After the **Append**, if the **Procedures** and **Views** collections are refreshed, the **View** will no longer be in the **Procedures** collection and will appear in the **Views** collection.</span></span>


