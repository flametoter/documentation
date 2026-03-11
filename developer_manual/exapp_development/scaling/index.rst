Scaling ExApps
==============

AppAPI delegates the scaling task to the ExApp itself.
This means that the ExApp must be designed in a way so that it is possible to scale vertically.
As for horizontal scaling, we recommend using Kubernetes for this.

You could also implement, for example, a Server-Worker architecture for basic scaling.
In this case, the Server is your ExApp and the Workers are the external machines that can work with the ExApp
using Nextcloud user authentication.
Additional clients (or workers) can be (optionally) added (or attached) to the ExApp
to increase the capacity and performance.

The rest of this section will explain how to setup and use Kubernetes for automated scaling.
Additional instructions are also provided if you have a GPU device for GPU scaling.


.. note::

	Currently, if a Deploy daemon is configured with GPUs available,
	AppAPI will by default attach all available GPU devices to each ExApp container on this Deploy daemon.
	This means that these GPUs are shared between all ExApps on the same Deploy daemon.
	Therefore, for the ExApps that require heavy use of GPUs,
	it is recommended to have a separate Deploy daemon (host) for them.


.. toctree::
	:maxdepth: 2

	KubernetesSetup
	KEDASetup
	AppAPIEmulation
