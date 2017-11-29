---
title: "EHostBindingPolicyModifyFlags — Wyliczenie"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: EHostBindingPolicyModifyFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: EHostBindingPolicyModifyFlags
helpviewer_keywords: EHostBindingPolicyModifyFlags enumeration [.NET Framework hosting]
ms.assetid: 0339af16-ee1d-48ec-837d-a79d9a9c89f8
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 42ff7ec7487be649e353b48e537cf1d8d45f6962
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/21/2017
---
# <a name="ehostbindingpolicymodifyflags-enumeration"></a><span data-ttu-id="4a634-102">EHostBindingPolicyModifyFlags — Wyliczenie</span><span class="sxs-lookup"><span data-stu-id="4a634-102">EHostBindingPolicyModifyFlags Enumeration</span></span>
<span data-ttu-id="4a634-103">Umożliwia hosta określić typ przekierowania, który środowisko uruchomieniowe języka wspólnego (CLR) należy wykonać podczas stosowania zmian zasad z zestawu źródła w zestawie docelowym.</span><span class="sxs-lookup"><span data-stu-id="4a634-103">Allows the host to specify the type of redirection the common language runtime (CLR) should perform when applying policy modifications from a source assembly to a target assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a634-104">Składnia</span><span class="sxs-lookup"><span data-stu-id="4a634-104">Syntax</span></span>  
  
```  
typedef enum _hostBindingPolicyModifyFlags {  
    HOST_BINDING_POLICY_MODIFY_DEFAULT  = 0,  
    HOST_BINDING_POLICY_MODIFY_CHAIN    = 1,  
    HOST_BINDING_POLICY_MODIFY_REMOVE   = 2,  
    HOST_BINDING_POLICY_MODIFY_MAX      = 3  
} EHostBindingPolicyModifyFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="4a634-105">Elementy członkowskie</span><span class="sxs-lookup"><span data-stu-id="4a634-105">Members</span></span>  
  
|<span data-ttu-id="4a634-106">Element członkowski</span><span class="sxs-lookup"><span data-stu-id="4a634-106">Member</span></span>|<span data-ttu-id="4a634-107">Opis</span><span class="sxs-lookup"><span data-stu-id="4a634-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_BINDING_POLICY_MODIFY_CHAIN`|<span data-ttu-id="4a634-108">Określa, że środowisko CLR będzie łańcucha wartości zasad zestawu źródła na tych funkcji w zestawie docelowym.</span><span class="sxs-lookup"><span data-stu-id="4a634-108">Specifies that the CLR will chain policy values of the source assembly onto those of the target assembly.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_DEFAULT`|<span data-ttu-id="4a634-109">Określa, że środowisko CLR będzie wykonywać domyślne działanie.</span><span class="sxs-lookup"><span data-stu-id="4a634-109">Specifies that the CLR will perform the default action.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_MAX`|<span data-ttu-id="4a634-110">Określa, że środowisko CLR będzie wartości zasad dla zestawu docelowego do maksymalnej wartości.</span><span class="sxs-lookup"><span data-stu-id="4a634-110">Specifies that the CLR will set the policy values of the target assembly to the maximum values.</span></span>|  
|`HOST_BINDING_POLICY_MODIFY_REMOVE`|<span data-ttu-id="4a634-111">Określa środowisko CLR spowoduje zastąpienie wartości zasad dla zestawu docelowego z tymi źródło zestawu.</span><span class="sxs-lookup"><span data-stu-id="4a634-111">Specifies that the CLR will replace policy values of the target assembly with those of the source assembly.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a634-112">Uwagi</span><span class="sxs-lookup"><span data-stu-id="4a634-112">Remarks</span></span>  
 <span data-ttu-id="4a634-113">[ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) metoda przyjmuje parametr typu `EHostBindingPolicyModifyFlags`.</span><span class="sxs-lookup"><span data-stu-id="4a634-113">The [ICLRHostBindingPolicyManager::ModifyApplicationPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md) method takes a parameter of type `EHostBindingPolicyModifyFlags`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a634-114">Wymagania</span><span class="sxs-lookup"><span data-stu-id="4a634-114">Requirements</span></span>  
 <span data-ttu-id="4a634-115">**Platformy:** zobacz [wymagania systemowe](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4a634-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a634-116">**Nagłówek:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="4a634-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4a634-117">**Biblioteka:** biblioteki MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4a634-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4a634-118">**Wersje programu .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a634-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a634-119">Zobacz też</span><span class="sxs-lookup"><span data-stu-id="4a634-119">See Also</span></span>  
 [<span data-ttu-id="4a634-120">ICLRHostBindingPolicyManager — interfejs</span><span class="sxs-lookup"><span data-stu-id="4a634-120">ICLRHostBindingPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostbindingpolicymanager-interface.md)  
 [<span data-ttu-id="4a634-121">Hosting — wyliczenia</span><span class="sxs-lookup"><span data-stu-id="4a634-121">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)