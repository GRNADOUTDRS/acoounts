# acoounts
 # Download and cache dependencies
  - restore_cache:
      keys:
      - v1-dependencies-{{ checksum "package.json" }}
      # fallback to using the latest cache if no exact match is found
      - v1-dependencies-

  - run: yarn install

  - save_cache:
      paths:
        - node_modules
      key: v1-dependencies-{{ checksum "package.json" }}
    
  # run tests!
  - run: yarn test
