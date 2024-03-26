# Github action to deploy SPA to AWS S3
Custom GitHub action using `docker` and `python`

## Usage

```yaml
      - name: Deploy site
        id: deploy
        uses: 'imhotepper/deploy-s3-docker-action'
        env:
          AWS_ACCESS_KEY_ID: ${{ secrets.AWS_ACCESS_KEY_ID }}
          AWS_SECRET_ACCESS_KEY: ${{ secrets.AWS_SECRET_ACCESS_KEY }}
        with:
          bucket: [your-s3-bucket-name]
          dist-folder: ./dist
          # bucket-region: eu-central-1

      - name: Output information
        run: |
          echo "Live url: ${{steps.deploy.outputs.website-url}}"  

```