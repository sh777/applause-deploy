# applause-deploy

## Install Weave Flux

kubectl create namespace flux

export GHUSER="sh777"
fluxctl install \
--git-user=${GHUSER} \
--git-email=withoutbug@gmail.com \
--git-url=git@github.com:${GHUSER}/applause-deploy \
--git-path=demo \
--namespace=flux | kubectl apply -f -

## Get the flux public key
fluxctl identity --k8s-fwd-ns flux

Open https://git.build.ingka.ikea.com/, navigate to your repoistory, go to Setting > Deploy keys, click on Add deploy key, give it a Title, check Allow write access, paste the Flux public key and click Add key.
