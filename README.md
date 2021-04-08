# github-action-publish-workflow-manifests
Dispatchery V2 GitHub Action - publish workflow manifests

## Usage

    jobs:
      process-workflows:
        runs-on: ubuntu-latest
        steps:
          - name: Copy workflow manifests
            uses: wistia/github-action-publish-workflow-manifests@v1
            with:
              repo_name: ${{ github.event.repository.name }}
              env: ${{ steps.build-images.outputs.env }}
              aws_account: ${{ env.AWS_ACCOUNT }}
              eks_cluster: ${{ env.EKS_CLUSTER }}
              gitops_repo: ${{ env.GITOPS_REPO }}
              gitops_actor: ${{ env.GITHUB_ACTOR }}
              gitops_token: ${{ secrets.BOT_TOKEN }}
              gitops_repo_account: ${{ env.GITOPS_REPO_ACCOUNT }}
              git_sha: ${{ github.sha }}
